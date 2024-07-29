# Synchronization Framework

The synchronization framework defines the components that allow Kuwaiba to obtain data from the actual network to keep the inventory up to date[^synchronization_framework].

To access the synchronization module, locate the ![others_icon](images/icons/others_icon.png) icon in the menu at the top, when you select it, a vertical menu will be displayed as shown in Figure 1, where you must select the `Synchronization Framework` option.

| ![access_module_sync](images/access_module.png) |
| :--: |
| ***Figure 1.** Access to the synchronization module.*|

Figure 2 presents the interface of the module. At the top, there are three options, marked in the red box, which are described below as a series of steps to follow in order to use the module effectively.

| ![module_sync](images/sync_module.png) |
| :--: |
| ***Figure 2.** Synchronization module.*|

* The `Data Source Templates` option allows the user to view, create or delete templates for loading source data. Selecting this option displays the view seen in Figure 3.
  
  | ![data_source_template_opt](images/data_source_template.png) |
  | :--: |
  | ***Figure 3.** Data Source Templates.*|

  To create a template, select the ![create_data_source_template](images/icons/add_icon.png) icon. When doing so, the information that allows the user to create a new template will appear, as illustrated in Figure 4. In this step, it is necessary to define the template name, description and properties.

  | ![create_template](images/create_data_source_template.png) |
  | :--: |
  | ***Figure 4.** Create template.*|

  To add properties, select the icon ![create_properties](images/icons/add_icon.png). Once the property name is set, press Enter to save the value. To delete a property, click on the icon ![delete_property](images/icons/delete_icon.png) next to each added property. Finally, to save the template, select the icon ![save_template](images/icons/save_icon.png).

  | ![add_properties](images/add_property_name.png) |
  | :--: |
  | ***Figure 5.** Create properties in template.*|

  The templates created are displayed in the list of templates, shown in Figure 3 (initially empty). This list is represented as a table including the name of the template, its description and the associated options. In this context, the only available option is indicated by the icon ![delete_template](images/icons/delete_icon.png), which allows you to delete the template. If you select a template from the list, you can view its contents and modify it, as illustrated in Figure 7.

  | ![template_added](images/templates_added.png) |
  | :--: |
  | ***Figure 6.** List of templates.*|

  | ![template_added](images/update_sync_template.png) |
  | :--: |
  | ***Figure 7.** Update template.*|

Once you have defined your templates, you can proceed with the synchronization process by object group or by a particular object.

* To define a synchronization process for a specific inventory object, locate and select the `Data Sources` button. This will take you to the view shown in Figure 8, where you will find a table (initially empty) with the data sources created. The data sources contain the specific information to retrieve the data from a particular device.

  | ![data_sources](images/data_sources.png) |
  | :--: |
  | ***Figure 8.** Data sources.*|

  To create a new data source, click on the ![create_data_source](images/icons/add_icon.png) button. Subsequently, a search bar will appear where you can find the inventory object by its name or by the class it belongs to.

  | ![data_sources_by_object](images/data_sources_by_object.png) |
  | :--: |
  | ***Figure 9.** Data sources by object.*|

  After selecting an object, the data sources associated with that object will appear in the table mentioned above. Because the selected object has no data sources, the list appears empty. To add a new data source, select button the ![create_data_source](images/icons/add_icon.png) again. On the right side of the screen, a form with the necessary information for its creation will appear. First, you must select an existing template. You can view the existing templates by clicking on ![template_list_icon](images/show_templates_icon.png), which will display a list.

  | ![search_object](images/create_data_source.png) |
  | :--: |
  | ***Figure 10.** Select template.*|

  After selecting the template, the properties defined in it will be displayed. To assign a value to them, double click on the property and define the desired value. Then press the Enter key to set it.

  | ![search_object](images/configure_data_source_common.png) |
  | :--: |
  | ***Figure 11.** Configure common properties values.*|

  In addition, you can add specific properties for an object by selecting specific properties. Similar to creating properties in templates, select ![create_specific_property](images/icons/add_icon.png) to add them.

  | ![search_object](images/configure_data_source_specific.png) |
  | :--: |
  | ***Figure 12.** Configure specific properties values.*|

  Finally, to save the data source I selected ![save_data_source](images/icons/save_icon.png) and the data source appears in the list mentioned in Figure 9.

  | ![search_object](images/added_new_data_source.png) |
  | :--: |
  | ***Figure 13.** List of data sources.*|

  The table in Figure 13 has four columns.

  * **Type** The type of data source (set by the template).
  * **Name** The name of the data source.
  * **Description** The description added to the data source.
  * **Options** Different actions that can be performed for the data source. It has four options which are detailed below.
    * The icon ![execute_data_source](images/icons/execute_sync_icon.png) executes the synchronization set for the selected object.
    * The icon ![add_to_group](images/icons/add_data_to_group_icon.png) allows you to add the data source to an existing synchronization group.

        | ![search_object](images/add_data_source_to_group.png) |
        | :--: |
        | ***Figure 14.** Add data source to group.*|

    * The icon ![delete_from_group](images/icons/release_data_from_group_icon.png) removes the data source from a synchronization group.
    * The icon ![delete_data_source](images/icons/delete_icon.png) removes the data source.

* Synchronizations by group are managed in `Sync Groups`, where you can search for the data sources of a previously created group or create a new synchronization group. Sync groups allow you to run a synchronization process for several inventory objects. For this, it is necessary to have data sources created, as explained above.
  
  | ![sync_by_groups](images/sync_groups.png) |
  |  :--: |
  | ***Figure 15.** Synchronization groups.*|

  To create a new group select the ![create_new_sync_group](images/icons/add_icon.png) button, which opens a pop-up window like the one shown in Figure 16, where you can add the group name, a description and add data sources.

  | ![create_sync_groups](images/create_sync_group.png) |
  |  :--: |
  | ***Figure 16.** Create a synchronization group.*|

  To view the data sources associated with a group, use the search bar on the sync groups screen. You can search for the group of interest by typing the group name in the search bar or by selecting it from the drop-down list by clicking ![show_groups_icon]. When you select a group, the associated data sources will appear in the table in Figure 17. This table has four columns:

  | ![create_sync_groups](images/data_sources_by_group.png) |
  |  :--: |
  | ***Figure 17.** Data sources by group.*|

  * **Name** Name of data source.
  * **Description** Description of the data source.
  * **Inventory Objects** Inventory object associated with the data source.
  * **Options** The actions that can be performed for each data source. It has only one option which is ![release_from_group](images/icons/release_from_group_icon.png) which removes the data source from the group.
  
  To modify a group's information, select the icon ![update_group_icon](images/icons/update_group_icon.png), which will open the window shown in Figure 18. In this window, the user can modify the group name, description and associated data sources, adding or deleting them as needed.

  | ![create_sync_groups](images/update_group.png) |
  |  :--: |
  | ***Figure 18.** Update group.*|

  To delete a group, select the icon ![delete_group](imgaes/../images/icons/delete_icon.png).

  Finally, you can execute the whole synchronization group by clicking on ![execute_sync_group](images/icons/execute_sync_icon.png) which executes all the data sources associated to the group. At the end of its execution, a window appears with the results obtained in the synchronization process.

## List of Parameters by Protocols

Currently, the synchronization module supports Simple Network Management Protocol (SNMP) and Secure Shell (SSH) protocols. The parameters that can be defined for the above protocols are shown below.

* **SNMP**
  
  | Parameter | Description |
  | ----------|------|
  | ipAddress | IP address of the system that will manage the SNMP devices. |
  | port | Port for SNMP.|
  | version | SNMP version. The possible values are: `2c`, `3`. The default value is `2c`. |
  | community | SNMP Version `2c` attribute community. Default value public. |
  | authProtocol | SNMP version `3` attribute authentication protocol. Possible values: `MD5`, `SHA`. |
  | authPass | SNMP version `3` attribute  authentication protocol pass phrase. |
  | securityLevel | SNMP version `3` attribute security level. Possible values: `noAuthNoPriv`, `authNoPriv`, `authPriv`. |
  | securityName | SNMP version `3` attribute security name. |
  | contextName | SNMP version `3` attribute context name. |
  | privacyProtocol | SNMP version `3` attribute privacy protocol. Possible values: `DES`, `AES`. |
  | privacyPass | SNMP version `3` attribute privacy protocol pass phrase. |

* **SSH**
  
  | Parameter  | Description |
  | ----------|------|
  | sshPort | SSH port. |
  | sshUser | Username used to log in to a remote server via SSH. |
  | sshPassword | Password associated with the `sshUser`. |

  [^synchronization_framework]: Synchronization Framework Overview: https://www.kuwaiba.org/docs/dev/sync/
