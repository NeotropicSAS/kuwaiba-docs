# Template Manager

In many scenarios, there are containment structures (see [Containment Manager](../containment/README.MD) for details) that are created repeatedly, such as `Building → Floor → Room → Rack`, or `ODF/DDF` with the same number of ports `(24/12/36/48/72/96/144)`, or simply equipment with the same set of attributes. For example, all routers of a certain model: the provider, slots, etc., will always be the same. Creating these elements from scratch each time would be a tedious task. For this reason, Kuwaiba provides the template manager module, which allows the creation of object templates from real inventory elements.

Figure 1 shows the structure of the module. In this example, a template is used to create cities that contain buildings, which in turn include rooms. For simplicity, only one city, building and one room are shown. When creating a template for a class, as demonstrated in the example with the *A Sample City* template, its association with the class is established through the *HAS_TEMPLATE* relationship. Additionally, the *INSTANCE_OF_SPECIAL* relationship is created to indicate that the template is a special instance of the class, since A Sample City will generate an instance of City.

Templates can contain other templates; in our example, we want a city to contain buildings. To achieve this, the *CHILD_OF* relationship is used to indicate that the A Sample Building template is a child, or is contained within, A Sample City. Similarly to the relationship between City and Building, the *A Sample Room* template is created to represent rooms within buildings. Thus, by using this template, this hierarchical structure will be generated in the inventory.

| ![Template Structure](images/template_manager_structure.png) |
|:--:|
| ***Figure 1.** Template manager structure* |

The template manager module, shown in Figure 2, belongs to the **Administration** category.

| ![Template Module](images/template_manager_menu.png) |
|:--:|
| ***Figure 2.** Template manager module* |

## Creating a Template
Once the module is open, to create a template, select the class for which you want to create the template in the selector located at the top left of the module's main window, as shown in Figure 3.

| ![Template Manager Selecting Class](images/template_manager_class_selection.png) |
|:--:|
| ***Figure 3.** Template manager selecting class* |

You can select any of the classes available in the application, except for abstract and list-type classes, as elements of these classes cannot be created.

Once the class is chosen, proceed to create the template using the button ![Template Module Btn Add Template](images/btn_add_template.png) The template creation window shown in Figure 4 will open. You must select the class if you have not already done so and assign a name to the template. Use a descriptive name, as this will be the one you see in the list of available templates.


| ![Template Creation Window](images/template_manager_new_template.png) |
|:--:|
| ***Figure 4.** Template creation window* |

Once the template is created, it will appear in the list of templates created for the selected class along with its actions, as shown in Figure 5.

| ![Template Module](images/template_manager_list.png) |
|:--:|
| ***Figure 5.** Template list* |

## Template Actions

### Deleting a Template

It is possible to delete templates created for a class. To do so, use the button ![Template Module Btn DElete Template](images/btn_delete_templatel.png)in the template actions shown in Figure 5. This will open the template deletion window shown in Figure 6. Click *OK* to delete it or *CANCEL* if you do not wish to proceed.

| ![Template Module](images/template_manager_delete_template.png) |
|:--:|
| ***Figure 6.** Template delete window* |

### Adding Elements
You can add **elements** or **special elements** to templates. The elements that can be added are determined by the containment configuration of the class see [Containment Manager](../containment/README.MD) for more details.

To add **elements** to the template, use the ![Template Module Btn Add Elements](images/btn_add_template.png) button in the template actions shown in Figure 5. If you want to add **special elements**, use the ![Template Module Btn Add Special Elements](images/btn_add_special_elements.png) button. This will display the menu shown in Figure 7, where you must select whether you want to create a single element or multiple elements. If the class does not have any elements or special elements assigned in its containment, you will not be able to add elements of this type to the template.

| ![Elements Options Menu](images/elements_options_menu.png) |
|:--:|
| ***Figure 7.** Elements options menu* |

#### Creating a Single Element
If you select to create a single element from the menu in Figure 7, the single element creation window shown in Figure 8 will open. Here, you will need to assign a name to the element and choose the class of the element to add. The available classes depend on the containment configuration of the class to which you are creating the element.

| ![Single Element Creation Window](images/template_manager_create_single_element.png) |
|:--:|
| ***Figure 8.** Single element creation window* |

#### Creating Multiple Elements

If you select to create multiple elements from the menu in Figure 7, the multiple elements creation window shown in Figure 9 will open.

| ![Multiple Elements Creation Window](images/template_manager_create_multiple_elements.png) |
|:--:|
| ***Figure 9.** Multiple elements creation window* |

Where you must choose the class of the element to add. The available classes depend on the containment configuration of the class to which you are creating the element (see [Containment Manager](../containment/README.MD) to more details about containment) and enter the **naming pattern** as detailed in [Appendix A](../../appendixes/appendix_a.md).

The result of using the **naming pattern** `[sequence(a,c)]`, useful for creating multiple elements like buildings in the *City* class,`[multiple-mirror(1,3)]`, useful for creating ports in the *SpliceBox* class and `[mirror(1,3)]`useful to create mirror ports in *ODF*,*SpliceBox* ** can be seen in Figures 10, 11  and 12 respectively.

| ![Example Sequence](images/example_pattern_frequency.png) |
|:--:|
| ***Figure 10.** Result of [sequence(a,c)]* |


| ![Example Mirror](images/example_pattern_multiple_mirror.png) |
|:--:|
| ***Figure 11.** Result of [multiple-mirror(1,3)]* |

| ![Example Mirror](images/example_pattern_mirror.png) |
|:--:|
| ***Figure 12.** Result of [mirror(1,3)]* |


## Template Element Management
Once the template elements are created, they will be added to the **template structure** section of the main module window, as shown in Figure 13.

| ![List of elements](images/template_manager_list_of_elements.png) |
|:--:|
| ***Figure 13.** List of elements* |

In this section, you can not only view the **elements** and the containment tree of the **multiple elements**, but also create new elements or special elements on existing ones or delete them using the![Template Module Btn Element Menu](images/btn_element_menu.png) button of the desired element, which will display the menu shown in Figure 14.

| ![Manage elements menu](images/template_manager_element_menu.png) |
|:--:|
| ***Figure 14.** Manage elements menu* |

This allows you to create containment structures as complex as needed, following the containment configuration of the class for which the template is created, as shown in Figure 15.

| ![Template Example](images/template_manager_example.png) |
|:--:|
| ***Figure 15.** Template Example* |

## Editing Properties of a Template or Elements
It is possible to edit the properties or elements of a template once they have been created. To do this, select the template or an element of the template you wish to edit. The properties sheet of the template, shown in Figure 16, or the properties of the template elements, shown in Figure 17, will appear on the right side of the main module window. Use this to edit the desired properties.

| ![Template Property Sheet](images/template_manager_edit_template_properties.png) |
|:--:|
| ***Figure 16.** Example of template property sheet* |


| ![Element Property Sheet](images/template_manager_element_edit_properties.png) |
|:--:|
| ***Figure 17.** Example of element property sheet* |

## Using the Template

You can create objects using the templates created in the template manager from any Kuwaiba module that has the **object options panel** as shown in Figure 18, explained in detail in the section [Object Options Panel](../../navigation/navman/README.md#object-options-panel) in Navigation module. This functionality is available in modules such as navigation, pools, etc. 

| ![Object Options Panel](images/object_opcions_panel.png) |
|:--:|
| ***Figure 18.** Object options panel* |

In the **Basic Options** section of the **Object Options Panel** you will find the options **New Object from Template** and **New Special Object from Template** as shown in Figure 19.

| ![Object To Create Objects From Template](images/select_options_to_create_objects.png) |
|:--:|
| ***Figure 19.** Options to create objects from template* |

When using them, the window for creating objects from a template, shown in Figure 20, will appear. The available classes depend on the containment configuration of the selected class.

| ![Object To Create Objects From Template Window](images/template_manager_create_object.png) |
|:--:|
| ***Figure 20.** Object creation window from template* |

For example, we use the *City* class and the previously created template *A sample city*. As a result, we create an object following the template, as observed in Figure 21.

| ![Example Object Created From Template](images/object_created_from_template.png) |
|:--:|
| ***Figure 21.** Sample object created from template* |