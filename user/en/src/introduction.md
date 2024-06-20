# Introduction

Kuwaiba sees an inventory system as a living entity, not growing only in terms of size, but also in structure and intelligence. The main reason being that business requirements change constantly and therefore, the application must be ready to respond to new scenarios. One of the key concepts that can help you unlock the potential of Kuwaiba is the [data model](./dmman/index.html). It provides a simplified representation of the network and the business from an operational point of view. It can be seen as the skeleton that supports the application, but a skeleton from which you can add, remove and change elements as you go. Later in this document you will be able to see what tools you can use to manage it. For now, just keep in mind that the better you design your data model and the more you get to know it, the more you will take advantage of the application.

Having said that, you will find four types of resources in a typical data model:

* **Physical**: Equipment, pipes, cables, fiber optics, facilities, parts and in general every physical asset from a port to a building.

* **Logical**: These are all the resources related to non-tangible technology assets. In this group fit timeslots, virtual circuits, VLANs, disk space, available bandwidth, etc. Other Non-physical: mostly software-related assets, such as licenses or virtual machines.

* **Administrative**: These are all those related to administrative tasks, human resources or commercial management. Customers, their services SLAs (and related parameters like availability or throughput), sales and technical staff assigned to those services, vendors and states belong to this category.

The Kuwaiba web client is a set of views (trees, topologies, editors) that allows to put together these elements based on business rules and user-defined models. Kuwaiba extends the concept of **CMDB** (Configuration Management Database, a place where you store objects that can hold configuration information or be subject to configuration themselves - so called Configuration Items- and their relationships) and enables you to perform network design tasks, support capacity management and provisioning workflows and assist field and customer service teams to improve response times.

Kuwaiba helps you model your network according to your needs, no matter if you’re an ISP, a carrier or just a guy with a large (or small!) IT infrastructure to manage. It’s open source, under active development and new models are added every release. You can contribute to the project by providing technical insight on a particular technology, testing, translating or just sending your feedback through forums[^1] and mailing lists[^2].

[^1]: Forums https://sourceforge.net/p/kuwaiba/discussion/
[^2]: mailing lists https://sourceforge.net/p/kuwaiba/mailman/
