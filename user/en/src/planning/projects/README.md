# Project Manager

The **Project Manager** module allows you to manage all your projects (network planning, maintenance, network roll-out, etc.), their activities and associated network resources in one place. The current version of the module offers basic functionality, which will be extended in the future.

To access the project module, locate the icon ![planning](images/icons/planning_icon.png) in the menu at the top of the screen. When clicked, a vertical menu will be displayed where the user can select the `Project Manager` option, which will direct the user to the interface shown in Figure 2.

| ![access_project_module](images/access_projects.png) |
| :--: |
| ***Figure 1.** Access to the projects module.* |

| ![project_module](images/projects_module.png) |
| :--: |
| ***Figure 2.** Projects module.* |

In Figure 2, a list of all existing projects should be displayed, as there are currently no projects in the inventory, the message `There are no projects so far` is displayed.

To create a project, you must first identify or create a pool. A pool is like a bag that can contain one or more projects (see more in [Pools][pools]). To create a pool or modify existing pools, select the icon ![manage_pools_icon](images/icons/manage_pools_icon.png) which will open a new pop-up window like the one shown in Figure 3.

| ![manage_pool](images/manage_pools.png) |
| :--: |
| ***Figure 3.** Management of project pools.* |

Figure 3 shows a list of all existing project pools. You can use the search bar to find pools matching specific terms. When you select a pool, the related information, such as name, description and list of contained projects, will appear on the right side of the window. Here, you can change the name or description of the pool by double-clicking on the property you want to change. In addition, you can delete the pool by clicking the button ![delete_pool](images/icons/delete_icon.png), which will also delete the projects contained in the selected pool.

| ![manage_pool_selected](images/manage_selected_pool.png) |
| :--: |
| ***Figure 4.** Management of selected pool.* |

To create a new pool, select the icon ![create_pool](images/icons/create_project_icon.png) shown in Figure 3. This will open a window like the one shown in Figure 5, where you can name, describe and select the type of pool to create. There are two types of project pools: `GeneralPurposeProject` and `NetworkProject`.

| ![create_pool](images/create_pool.png) |
| :--: |
| ***Figure 5.** Create a pool.* |

To create a project, select the icon ![create_project](images/icons/create_project_icon.png) which opens a pop-up window like the one shown in Figure 6, where you must select an existing Project Pool, the project name and you can add a description to it.

| ![create_project](images/create_project.png) |
| :--: |
| ***Figure 6.** Create a project.* |

The created project is added to the list of projects shown in Figure 2. Selecting a specific project in Figure 7 will display the information related to that project, as indicated in Figure 8 and explained below.

* **name.** Project name.
* **startDate.** Project start date. Default is `Wed 31 Dec 1969`.
* **status.** Project status. This attribute is a list type attribute (for more information see chapter [List Type Manager][list_type_manager]).
* **notes.** Additional information that the user adds about the project.
* **projectManager.** Person in charge of the project.
* **creationDate.** Date of creation of the project.

| ![projects_list](images/projects_module_updated.png) |
| :--: |
| ***Figure 7.** List of projects.* |

| ![project_information](images/project_information.png) |
| :--: |
| ***Figure 8.** Project information.* |

In the upper right part of Figure 8, there are 6 buttons, which are detailed below.

| ![project_options](images/project_options.png) |
| :--: |
| ***Figure 9.** Project options.* |

* The button ![delete_project_icon](images/icons/delete_icon.png) deletes a project.
* The icon ![manage_activities_icon](images/icons/manage_pools_icon.png) controls the project activities. When selecting this button, a window like the one shown in Figure 10 appears.
  
    | ![manage_activities](images/manage_activities.png) |
    | :--: |
    | ***Figure 10.** Project activity manager.* |

    To create a new project activity, select the ![create_activity_icon](images/icons/create_project_icon.png) icon displayed in Figure 10. This will open the window illustrated in Figure 11, where you can add the name of the activity and select its type, which can be `AuditActivity`, `DesignActivity`, `GeneralPurposeActivity`, `PlanningActivity` or `RollOutActivity`.

    After creating the activity, all activities will be listed as shown in Figure 11. When selecting an activity, the associated information will be displayed on the right side of the screen. To modify any of the attributes, you can double-click on the attribute you want to change.

    | ![activities](images/project_activities_options.png) |
    | :--: |
    | ***Figure 11.** Project activities.* |

  * **name.** Name of project activity.
  * **activityType.** Type of activity.
  * **sequecing.** Activity number.
  * **status.** Activity status.
  * **notes.** Notes on the activity.
  * **startDate.** Start date of activity.
  * **endDate.** Date of completion of the activity.
  * **lastUpdate.** Date of last activity update
  * **duration.** Duration of the activity.
  * **cost.** Cost of the activity.
  * **owner.** Owner of the activity.
  * **risk.** Activity risk.
  * **creationDate.** Date of creation of the activity.

    In addition, a project activity can be deleted by selecting the icon ![delete_activity](images/icons/delete_icon.png) shown in Figure 11. You can also check if there are any reports related to that activity by clicking on the button ![reports](images/icons/reports_icon.png).

* The icon ![reports](images/icons/reports_icon.png) allows you to visualize the reports available for the projects.
* The button ![information](images/icons/show_project_information_icon.png) displays information about the project object, i.e., its identifier, the class it belongs to and its content hierarchy.

    | ![project_information](images/project_information_add.png) |
    | :--: |
    | ***Figure 12.** Project Object Information.* |

* The icon ![copy_project_icon](images/icons/copy_project_icon.png) allows you to copy the project to another project pool. To do this, selecting the button opens the window shown in Figure 13, where you can select the pool to which you want to copy the project.
  
    | ![copy_project](images/copy_project.png) |
    | :--: |
    | ***Figure 13.** Copy project.* |

* The button ![move_project](images/icons/move_project_icon.png) moves the project to another project pool by selecting the new pool, as indicated in Figure 14.

    | ![move_project](images/move_project.png) |
    | :--: |
    | ***Figure 14.** Move project.* |

In Figures 13 and 14, you have the option to create a new project pool in case you do not want to select an existing one, to do so click on the icon ![create_pool](images/icons/create_project_icon.png) which opens the window presented in Figure 5.

In Figure 8, under the project information, there is the Related Resources section, which shows the list of objects related to the project. In this case, it is empty since there are no objects related to the project. To relate an object to an existing project, locate the Object Options Panel related to the object. In the Advanced Actions section, you will find the Relate to Project option, as illustrated in Figure 15.

| ![relate_object_to_project_action](images/relate_to_project_action.png) |
| :--: |
| ***Figure 15.** Action to relate an object to a project.* |

When selecting the commented option, a new window appears (Figure 16), where the user can type the name of the project or select it from the drop-down list by clicking on the icon ![project_list](images/icons/project_list_icon.png).

| ![relate_object_to_project_action](images/select_project.png) |
| :--: |
| ***Figure 16.** Project selection.* |

If you reload the project module and select the project again, it appears in the `Related Resources` section the related objects. To the right of each object there are 3 buttons.

| ![relate_object_to_project_action](images/related_resources.png) |
| :--: |
| ***Figure 17.** Related resources to project.* |

* The button ![open_object_options_panel](images/icons/dashboard_icon.png) opens the Object Dashboard in a new window (For more information see the [Navigation][navigation] chapter).
* The button ![more_information](images/icons/show_more_info_icon.png) opens a window with the object's identifier, the class to which it belongs and its content hierarchy, as demonstrated in Figure 18.

    | ![object_information](images/object_information.png) |
    | :--: |
    | ***Figure 18.** Object information.* |

* The icon ![release_from_project](images/icons/release_relation_project.png) removes the relationship between the object and the project.

[pools]: ../../navigation/pools/index.hml
[list_type_manager]: ../../administration/ltman/index.html
[navigation]: ../../navigation/navman/index.html
