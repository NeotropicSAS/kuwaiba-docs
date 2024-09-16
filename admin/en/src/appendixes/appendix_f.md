# Appendix F. Configure Attachment Size

An attachment is a file directly associated with an inventory object or list-type items linked to the object. These files can be documents, images, or relevant settings, and can be viewed, added, deleted, or downloaded for easy management and access.

To ensure efficient management of these attachments, it is essential to configure the maximum size allowed.

> **Note**
>
> The value is specified in MB, and you only need to adjust this value as needed. The default value is 10 MB.
>

Open your application.properties file and modify the following lines:

1. Maximum File Size:
   
   This property sets the maximum size for individual files that can be uploaded.

    ``` bash
       spring.servlet.multipart.max-file-size=10MB
    ```

2. Maximum Request Size:
   
   This property sets the maximum size for the entire multipart request.

    ``` bash
       spring.servlet.multipart.max-request-size=10MB
    ```

    > **Note**
    >
    > `Maximun File Size` and `Maximun Request Size` should be configured in accordance with the `Maximun Attachment Size`.
    >
    

3. Maximum Attachment Size:
   
   This property sets the maximum allowed size for attachments within the system.

    ``` bash
       bem.max-attachment-size=10
    ```
By adjusting these limits, the system can adapt to the specific needs of the inventory objects being managed, allowing for the storage and access of relevant attachments without exceeding the system’s capabilities.

