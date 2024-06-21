# Installation
## Standalone
### Requirements
#### Java Development Kit
JDK 11 is recommended, newer versions have not been tested and might not work. We recommend [OpenJDK](https://www.openjdk.org) and it's available in most distros, however, if you are struggling to find the right version on your package repository, Several vendors offer pre-compiled builds (including [Microsoft](https://learn.microsoft.com/en-us/java/openjdk/), [Amazon](https://docs.aws.amazon.com/corretto/latest/corretto-11-ug/downloads-list.html) and [OpenLogic](https://www.openlogic.com/openjdk-downloads)). We will use Amazon's JDK in this manual, but the instructions should apply to any other distribution. Unzip the installation package and copy it to your preferred location or install it using your package manager tools if a suitable installer is provider. This guide will assume you did the former.
#### The Server Application Bundle
Download the latest 2.1.x installation package from [SourceForge](https://sourceforge.net/projects/kuwaiba/files/Version%202.x/). Let's take a look at the contents:

   ![Kuwaiba 2.1.1 installation package contents](images/installation_package.png)

* **data:** Contains the directory structure where the database and other files are stored by default. This structure can be customized via configuration variables later. If you don't want to make changes to the default configuration, create the directory `/data`, copy the contents of `data` inside, and make sure the user running Kuwaiba has read and write permissions.
* **dbs:** Contains sample databases used to bootstrap the system. The `database 01` is completely empty, save for the default data model. It has no containment structure, sample objects or list types. This database is recommended for those already familiar with the platform and those who are ready to run a production instance. The `database 02` is no longer maintained and will be most likely removed in the future. It contains the same as the `database 02` plus a basic containment structure. `The database 03` is recommended for those willing to explore the features in Kuwaiba. It contains examples of several technologies, layouts, list types, validators, filters, configuration variables, topologies, views, reports and automated tasks, among many other goodies.
* **kuwaiba_server_2.1.x-stable.jar:** This file is the actual application. It has an embedded Tomcat server, so you don't need any other third-party software to run it. The extension of this file is `.jar`, but it's a regular `.zip` file, and you can open it with the archive manager of your preference. Inside you will find all the stylesheets and images to change the appearance of the UI.

![Contents of the file kuwaiba_server_2.1.x-stable.jar](images/application_jar_contents.png)

The most important file is `application.properties`. It contains several configuration variables that govern the behavior of Kuwaiba as shown in the table below. You can change the values to your convenience and pack the `.jar` file again (most archive managers will repack the file when you save the text file).

| Variable Name | Default Value   |Description   |
| ------------- | ------------- | ------------- |
| server.port | `8080` |The port where the server will run. Note that this port is used to serve the UI, but it is different from that used to serve the web service |
| ws.port | `8081` |The port where the SOAP-based web service will listen |
| db.port | ``6677`` | Database port, if applicable. The default value is not the same default Neo4J's server port. Connections to this port from other hosts rather than localhost will be denied |
| spring.devtools.add-properties | `false` |Enable/disable Spring devtools. They're disabled automatically for all `jar` builds, but not for `war` files |
| general.corporate-logo | `http://neotropic.co/img/logo_small.png` | Corporate Logo URL. To be used primarily in reports and branding-related features |
| db.path | `/data/db/kuwaiba.db` | Database path |
| aem.backgrounds-path | ``/data/img/backgrounds`` | Path of the folder where background images for Object Views are saved |
| bem.attachments-path | ``/data/files/attachments`` | Path of the folder where files attached to inventory objects are stored |
| spring.scheduler.enabled | ``true`` | Enables/disables the job scheduler service |

### Running the Server
The simplest method starts the server in foreground and logs in the standard output:
```bash
$ /path/to/java/installation/dir/bin/java -jar /path/to/kuwaiba/kuwaiba_server_2.1.x-stable.jar
```

The [nohup](https://en.wikipedia.org/wiki/Nohup) command allows you to launch the server so that it is not terminated once you logout from the terminal. In this case, unless you redirect the output, the application will log to `/home/<user>/nohup.out`:
```bash
$ nohup /path/to/java/installation/dir/bin/java -jar kuwaiba_server_2.1-stable.jar&
```

In production environments it is highly recommended to create a special, restricted user to run the server. To run the server as that user, you can use the following command (application messages will be logged in `/home/YOURUSER/nohup.out`):
```bash
$ sudo runuser -u YOURUSER -- nohup /path/to/java/installation/dir/bin/java -jar kuwaiba_server_2.1-stable.jar&
```
[Appendix B](#appendix-b-starting-the-server-on-boot) discusses how to configure the server to start on boot.

## Deploying on an Existing Application Server
## Docker
### Pulling the Image

For nightly builds (which are not really generated nightly, but at least once a week), use:
```bash
$ docker pull neotropic/kuwaiba:v2.1-nightly
```
### Deployment
#### Starting the Container

The container exposes 2 ports: 8080 (application) and 8081 (SOAP-based web service). You can use the following command to run the container and map those ports to the host machine.
```bash
$ docker run -dp 8080-8081:8080-8081 --name kuwaiba-server neotropic/kuwaiba:v2.1-nightly
```
Now it's possible to access the application by going to http://localhost:8080/kuwaiba⁠, or to access the SOAP-based web service API WSDL at http://localhost:8081/kuwaiba/KuwaibaService?wsdl⁠

#### Using a Custom Database

To avoid losing information across containers when you update an image, you can mount a custom database (thus overriding the stock one) located in your host machine and reuse it in different containers:

```bash
$ docker run -dp 8080-8081:8080-8081 --name kuwaiba-server -v /path/to/your/custom/database:/data/db/kuwaiba.db neotropic/kuwaiba:v2.1-nightly
```
Make sure the user used to run the container has write access on ``/path/to/your/custom/database``. You can download empty or sample databases from the [Sourceforge repository](https://sourceforge.net/p/kuwaiba/code/HEAD/tree/server/trunk/dbs/)⁠

#### Additional Information
* **Default Server Credentials:** admin/kuwaiba. There are several other users used to showcase the Process Manager capabilities in ``database 03``. You can check them out in the **User Manager** module. Their passwords are also ``kuwaiba``.
* **Data Directory:** /data
* **Application Directory:** /opt/programs

### Generate Your Own Image
* Fetch the Dockerfile from the [project repository⁠](https://sourceforge.net/p/kuwaiba/code/HEAD/tree/server/trunk/docker/) on SourceForge. Alternatively, you can also download the docker compose file from the same repository⁠
* Customize the Dockerfile depending on your needs.
* Build the image with:
```bash
$ docker build -t REPOSITORY_NAME:TAG .
```
where REPOSITORY_NAME is the name of the repository where the image will be placed and TAG is the tag for such container. Instead, you can also use the docker compose file like this:
```bash
$ docker compose -f kuwaiba.yaml up
```