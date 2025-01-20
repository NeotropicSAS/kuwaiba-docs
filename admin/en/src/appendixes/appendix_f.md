# Appendix F. Configuring the Max Attachment Size

An attachment is a file directly associated with an inventory object or a list-type item (which in turn will be linked to several objects e.g. a router installation manual file attached to a list type item representing its model will be available to all routers of said model). These files can be documents, images or relevant settings, and can be downloaded, added or deleted at any moment.

To ensure that the storage endpoint used to store the files won't be abused or overwhelmed, the attachments size limit is capped and configurable.

> **Note**
>
> The value is specified in MB, and you only need to adjust this value as needed. The default value is 10 MB.
>

Open your application.properties file and modify the following lines:

1. Set the max file size at application server level. This property sets the maximum size for individual files that can be uploaded.

    ``` bash
       spring.servlet.multipart.max-file-size=10MB
    ```

2. Set the max (HTTP) request size at application server level. This property sets the maximum size for the entire multipart request.

    ``` bash
       spring.servlet.multipart.max-request-size=10MB
    ```

    > **Note**
    >
    > **Maximum File Size** and **Maximum Request Size** should be configured in accordance with the **Maximum Attachment Size**, as explained in the next step.
    >
    

3. Set the max file size at application level. This property sets the maximum allowed size for attachments within the application. This restriction will apply to all **Persistence API** calls related to attachment handling, regardless if they are consumed through the northbound interfaces or automation procedures (such as tasks in the Task Manager).

    ``` bash
       bem.max-attachment-size=10
    ```

