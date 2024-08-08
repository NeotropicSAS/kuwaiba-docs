# Service Manager

The Service Manager allows you to organize all the services in pools. These pools of services belong to customers, these customers are at the same time organized in pools. To open the Services Manager look at the menu [Figure 1][figure-1].

| ![Service manager module][figure-1] |
|:--:|
| ***Figure 1.** Service manager module* |

[figure-1]: images/figure-service-manager-module.png

To start using the Service Manager you must create a pool of customers [Figure 2][figure-2]; depending on the loaded data model you can create pools of any subclass of `GenericCustomer` (see [Data Model Manager][dmman] if you need to create a different kind of customers).

[dmman]: ../../administration/dmman/index.html

| ![New customer pool][figure-2] |
|:--:|
| ***Figure 2.** New customer pool* |

[figure-2]: images/figure-new-customer-pool.png

1. Click the `Manage Customer Pools` button.
2. Click the `New Customer Pool` button.
3. Set the name.
4. Click the `OK` button.
5. Click the `Close` button.

Once you create your pool of customers you can create new customers, [delete the created pool](#delete-actions) or [show its id](#show-object-id) or [search](#search); as you can see in the [Figure 3][figure-3] you are able to create new customers with type any subclass of `GenericCustomer`.

| ![New customer][figure-3] |
|:--:|
| ***Figure 3.** New customer* |

[figure-3]: images/figure-new-customer.png

1. Click the `New Customer` button.
2. Set the type.
3. Set the name.
4. Click the `OK` button.

Why can we create new customers of the class `TelecomunicationsOperator` if the class of objects of the pool we created was `GenericCustomer`? Well, we can create customers of that class because `TelecomunicationsOperator` is a subclass of `GenericCorporateCustomer` and `GenericCorporateCustomer` is a subclass of `GenericCustomer` - this is defined in the data model [Figure 4][figure-4], (see [Data Model Manager][dmman] if you need to adjust the model to your needs).

| ![GenericCustomer subclasses][figure-4] |
|:--:|
| ***Figure 4.** GenericCustomer subclasses* |

[figure-4]: images/figure-generic-customer-subclases.png

Now you can create a pool of services inside a customer [Figure 5][figure-5] or [delete the customer](#delete-actions) or [show its id](#show-object-id) or [search](#search).

| ![New service pool][figure-5] |
|:--:|
| ***Figure 5.** New service pool* |

[figure-5]: images/figure-new-service-pool.png

1. Select customer.
2. Click the `Manage Service Pools` button.
3. Click the `New Service Pool` button.
4. Set the name.
5. Click the `OK` button.
6. Click the `Close` button.

Every pool of service has a name and a description, these properties could be changed later in the property sheet [Figure 6][figure-6], just selecting the pool of services and editing the values of its attributes.

| ![Service pool property sheet][figure-6] |
|:--:|
| ***Figure 6.** Service pool property sheet* |

[figure-6]: images/figure-service-pool-property-sheet.png

Once the pool of services has been created your are able to create services in it, just select the pool and select the kind of service you want to add [Figure 7][figure-7].

| ![New service][figure-7] |
|:--:|
| ***Figure 7.** New service* |

[figure-7]: images/figure-new-service.png

1. Select service pool.
2. Click the `New Service` button.
3. Set the type.
4. Set the name.
5. Click the `OK` button.

> **Note**
>
> Services can also be created using templates ![New service from template][button-new-service-from-template] in which you can define the characteristics of the services such as price, bandwidth and all the common elements for the services for example in a service catalog. See the [Template Manager][templates].

As mentioned before, if you need a new kind of service that is not listed, just add it to your data model [Figure 8][figure-8] (see [Data Model Manager][dmman]).

| ![GenericService subclasses][figure-8] |
|:--:|
| ***Figure 8.** GenericService subclasses* |

[figure-8]: images/figure-generic-service-subclasses.png

[button-new-service-from-template]: images/button-new-service-from-template.png
[templates]: ../../administration/templateman/index.html

After you finish creating and organizing all of your customers and services in pools, you can go to the [Navigation Tree][navman] or to the [IP Address Manager][ipam], and relate objects to a service, as you can see in [Figure 9][figure-9]. Just select the object and select the action `Relate to Service` in the [Object Option Panel][object-options-panel].

[object-options-panel]: ../../navigation/navman/index.html#object-options-panel

[navman]: ../../navigation/navman/index.html
[ipam]: ../../logical/ipman/index.html

| ![Relate to service][figure-9] |
|:--:|
| ***Figure 9.** Relate to service* |

[figure-9]: images/figure-relate-to-service.png

Using the Service Manager you can also relate objects to services using the `Relate to Network Resource` action [Figure 10][figure-10].

| ![Relate to network resource][figure-10] |
|:--:|
| ***Figure 10.** Relate to network resource* |

[figure-10]: images/figure-relate-to-network-resource.png

To view objects related to a service, use the Network Resources Explorer [Figure 11][figure-11] in the [Object Options Panel][object-options-panel].

| ![Network resources explorer][figure-11] |
|:--:|
| ***Figure 11.** Network resources explorer* |

[figure-11]: images/figure-network-resources-explorer.png

Of course you are also able to release an object from a service. After associating an object to a service, if you want to release that relationship you need select the object an select `Release from..` action [Figure 12][figure-12] in the [Object Options Panel][object-options-panel].

> **Note**
>
> To release from service you can also use the Network resources explorer [Figure 11][figure-11] using the `Release from Service` button ![Release from Service][release-from-service].

| ![Release from service][figure-12] |
|:--:|
| ***Figure 12.** Release from service* |

[figure-12]: images/figure-release-from-service.png

[release-from-service]: images/button-release-from-service.png

> **Important**
>
> You are not able to delete an object if the object is associated to a service; if you want to delete that object you should first release the relationship with the service.

## Delete Actions

To delete customer pool, customers, service pool and services use the delete button ![delete button][delete-button] in the service manager.

[delete-button]: images/button-delete.png

| ![Delete customer][figure-13] |
|:--:|
| ***Figure 13.** Delete customer* |

[figure-13]: images/figure-delete-customer.png

Customers [Figure 13][figure-13] and services [Figure 14][figure-14] can also be deleted using the delete action in the [Object Options Panel][object-options-panel].

| ![Delete service][figure-14] |
|:--:|
| ***Figure 14.** Delete service* |

[figure-14]: images/figure-delete-service.png

## Show Object Id

To obtain information about customer or services such as the id, select the object and click on the `Show More Information` button [Figure 15][figure-15].

| ![Show more information][figure-15] |
|:--:|
| ***Figure 15.** Show more information* |

[figure-15]: images/figure-show-more-information.png

## Search

To search for a pool of customers, customers, pool of services and services, the search fields are used [Figure 16][figure-16].The customer and service pools are filtered only by name and the customers and services are filtered by name and type.

| ![Search field][figure-16] |
|:--:|
| ***Figure 16.** Search field* |

[figure-16]: images/field-search.png
