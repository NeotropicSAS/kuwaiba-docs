# Tasks Manager
The *Task Manager* facilitates the creation, execution, and notification of tasks. It provides a flexible for defining scripts to be executed under various conditions and notifying users. 

This module is part of the *Administration* category, as shown in Figure 1.

|![Task Manager Module](images/taskman_module.png)|
|:--:|
| ***Figure 1.** Task manager module* |

Once opened, we will see the main window of the module, as shown in Figure 2. From here, we can view the tasks currently created in the application.

|![Task Main Window](images/taskman_main_window.png)|
|:--:|
| ***Figure 2.** Tasks manager main window* |

## Task

A task consists of the following properties: 

| Property           | Description |
|--------------------|----------------------------------------|
| **Name**           | Name of the task |
| **Description**    | Description of the task |
| **Enable**         | Flag to enable or disable the execution of the task |
| **CommitOnExecute**| Flag to enable or disable if this task commit the changes in data base (if any) after its execution |
| **Script** | The Groovy script to be executed by this task. |
| **Parameters**    | List of parameters as a set of parameter name/value pairs used in the script |
| **StartTime** | The exact time and date the task should be executed.(Optional) |
| **EveryXMinutes** | Interval should this task be executed.(Optional) |
| **ExecutionType** | How the task should be executed.(Optional) |
| **Email** | The email of the person or group that will receive the notification (Optional). |
| **NotificationType** | What type of notification should the subscribed.(Optional) |

### Tasks Action 
#### Create Tasks
To create a task, use the![Btn Create Task](images/btn_create_tasks.png)button in the main window of the module. The task creation window shown in Figure 3 will open. You will need to enter the name and description of the task. It is advisable to use a descriptive name, as this will be the name displayed in the list of available task. Click *OK* to create the task or *CANCEL* if you do not wish to proceed.

|![Create Task Window](images/taskman_create_task_window.png)|
|:--:|
| ***Figure 3.** Create task window* |

Once created, the task will appear in the list of available tasks within the application, here you can also search task by name as shown in Figure 4. 

|![Group List](images/taskman_list_of_tasks.png)|
|:--:|
| ***Figure 4.** Group list* |

When selecting a task the main module window will display the information and buttons actions as shown in Figure 5.

|![User Information](images/tasman_task_information.png)|
|:--:|
| ***Figure 5.** Task information* |

#### Script
In the script section shown in Figure 5, you can define your own scripts, which can range from custom inventory queries to the perform complex actions.

> **Information**
It is out of the scope of this document to teach how to code scripts, however, you can find more detail and examples in the scripts available in this [repository](https://sourceforge.net/p/kuwaiba/code/HEAD/tree/server/trunk/scripts/tasks/).

##### Script Parameters
It is important to note that most scripts will require input parameters. These parameters can be easily added to the task so that the user can fill them in before executing the task. To manage the parameters, click on the![Btn manage Parameters](images/btn_manage_parameters.png)button. The parameter management window shown in Figure 6 will open, allowing you to create, edit, and delete parameters.

|![Manage Parameters Window](images/taskman_manage_parameters_window.png)|
|:--:|
| ***Figure 6.** Manage parameters window* |

To create a parameter, use the![Btn Create Task](images/btn_create_tasks.png)button in the main parameter management window. The window to add a new parameter, shown in Figure 7, will open. Enter the name of the parameter to be used in the script and its value. Click *OK* to create it or *Cancel* if you decide not to proceed.

|![New Parameters Window](images/taskman_new_parameter_window.png)|
|:--:|
| ***Figure 7.** New parameters window* |

Once created, the parameter will be visible in the parameter management window, as shown in the example in Figure 8. You can edit its properties using the![Btn Update](images/btn_update.png)button or delete it with the![Btn Delete Parameter](images/btn_delete.png)button seen in Figure 8.

|![Parameter Example](images/manage_parameters.png)|
|:--:|
| ***Figure 8.** Parameter example* |

##### Save And Execute Script
Once the script and its parameters have been created, as shown in the example in Figure 9, you can save the script changes using the![Btn Save](images/btn_save_task_changes.png)button seen in Figure 5.  

|![Script Example](images/example_script.png)|
|:--:|
| ***Figure 9.** Basic example of script and parameters* |

Or use the![Btn Execute](images/btn_execute.png)button seen in Figure 5 to save the script changes and execute your script.The execution result will be displayed in the popup window, si la ejecución fue exitosa el resaltado sera resaltado en color verde como se muestra en la Figura 10.

|![Script Execution Example](images/script_execution.png)|
|:--:|
| ***Figure 10.** Script execution* |

If errors occur during the script execution, the result will be highlighted in red, as shown in Figure 11.

|![Fali Script Execution Example](images/script_execution_fail.png)|
|:--:|
| ***Figure 11.** Failed script execution* |

##### Commit On Execute
If you want the changes made by the script to be saved in the database after it is executed, enable *CommitOnExecute* by toggling the switch seen in Figure 5. from disabled![Disable commit](images/btn_commit_disable.png)to enabled![Enable commit](images/btn_commit_enable.png)

> **Warning**
> The changes made by tasks in the database can break things if your code is wrong. Ensure that the script execution was successful before enabling this feature. By default, CommitOnExecute is set to false.

#### Update Task Properties
To edit the properties of a task, use the![Btn Update](images/btn_update.png)button seen in Figure 5. The task update window shown in Figure 12 will open. Edit the desired properties and click *OK* to update them or *CANCEL* if you do not wish to proceed.

|![Update Task](images/taskman_update_task_window.png)|
|:--:|
| ***Figure 12.** Update task properties window* |

#### Delete Task 
To delete a task, use the![Btn Create Task](images/btn_delete.png)button seen in Figure 5. The confirmation window shown in Figure 13 will open. Click *OK* to delete it or *Cancel* if you decide not to proceed.

|![Delete Task](images/taskman_delete_task.png)|
|:--:|
| ***Figure 13.** Delete task confirmation window* |

#### Schedule Task
It is possible to schedule task execution using the scheduling module, explained in detail in the [Scheduling module](../scheduling/README.md) section.  