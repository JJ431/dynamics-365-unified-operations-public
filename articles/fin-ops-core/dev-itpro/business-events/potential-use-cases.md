---
# required metadata

title: Use cases for business events
description: This topic lists use cases for business events.
author: Sunil-Garg
manager: AnnBe
ms.date: 10/14/2019
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 

# optional metadata

# ms.search.form:  [Operations AOT form name to tie this topic to]
audience: IT Pro
# ms.devlang: 
ms.reviewer: sericks
ms.search.scope: Operations, Core
# ms.custom: 
ms.search.region: Global
# ms.search.industry: 
ms.author: sunilg
ms.search.validFrom: Platform update 24
ms.dyn365.ops.version: 2019-02-28
---

# Use cases for business events

[!include[banner](../includes/banner.md)]

The following are potential uses cases for business events. This is by no means an exhaustive list of the potential use cases. It should also be noted that some of these use cases may not have been implemented yet either by Microsoft or other organizations. These are meant to provide ideas and help with understanding business events.

| Business process  | Use case                         | Value  |
|-----------------------|--------------------------------------|------------|
| Procurement | The procurement process frequently relies on manual intervention, so automating this process should increase procurement manager productivity.             | You can make the procurement process more efficient by alerting procurement managers when quotation requests are sent, allowing for prompt follow up and faster engagement. The goal is to have procurement managers follow up within three days and possibly create a Flow that automates this follow up. |
| Procurement | Many organizations use manual processes to communicate internally and externally about production orders. Some organizations have complex approval processes for production orders, and need quick and easy ways to review and approve orders. | By creating business events that are triggered when production orders are updated, you can help improve communications between the back office and the production floor. When integration is required with third-party systems for production, the business events can also be used to help simplify the integration process. |
| Reporting | Managers are not informed about newly created financial reports. As a result, managers might analyze and make decisions based on outdated data.          | You can make the reporting process more efficient by alerting managers when financial reports are sent, allowing for prompt follow up and faster engagement. The goal is to have managers follow up within three days and possibly create a Flow that automates this follow-up.                            |
| Customer master | When a new customer is created, a credit limit check is needed. If something could automatically trigger an API that subscribes to a credit limit, and then check the website and import specific credit limit check fields, such as limit amount and rating. At the same time, an approval Flow needs to start so that the customer account can be used after approval from management. | This is required by many companies, especially in the retail area. This would be beneficial because partners develop customizations for this purpose.   |
| Month end close | The month-end closing schedule is a simple list that does not allow automatic actions. If functionality could be created to inform a group of people about tasks that have been completed and verified as complete, then a different group of people could start working.    | Use real-life scenarios to enhance the currently static and difficult to use month-end closing workspace. One such use case is explained in detail in [Business events in Financial Period Close](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/business-events/how-to/period-close). |
| Month end close | If functionality could be created to trigger a flow when the status of a period is changed – either opened or closed.  | Users are not automatically informed when new periods are opened after the month-end close is completed and they are allowed to start recording transactions in the new period.                             |
| Vendor master | If you are using the supplier (vendor) collaboration workspace, there is no automated way to inform the supplier that a new record has been created or existing records have been updated. This is an issue with requests for quotation and purchase orders. This means that the supplier would need to review the supplier collaboration workspace in case there are issues. | Using business events, the supplier portal functionality will provide improved productivity and efficiency by removing the need for additional correspondence between the supplier and the application. This is a true collaboration and will lead to supply chain efficiency. Without this functionality, the organization must follow up on all new requests or updates with phone calls or emails to the suppliers. This improves the supplier collaboration workspace. |
| Vendor master | Many organizations use manual, offline, and paper-based processes to manage vendors. Additionally, in many organizations, there are "gate keepers" that manage the master data. When updates occur to vendor master data, communication throughout the organization is limited or complex. | By integrating with Microsoft Flow and creating business events for actions and events that regularly occur with vendor master data, you can help improve the overall vendor onboarding process. You can also help improve internal communications within your organization and automate business processes with your trade partners. |
| Sales quotation | A quotation is placed for a personalized product. After the quotation is won this needs to become a real product. Requests are sent to a Data team (using PowerApps or Office) to create the item. After the item has been manually created, the item on the line is updated and the quote triggers the creation of a sales order. Currently, when the item is created, the approach is to wait for the data integrator to copy it to Common Data Service. Monitors are set to find new entries on Common Data Service and compare the unique references to any open numbers. Ideally, an item created business event exists, which is extended so that it has the unique identifier. This event is then subscribed to (in Flow or PowerApps) and immediately updates the quote line. | Using business events, the business would be able to update the won quote with the new product when the new product is created. This removes possible delays, manual updates, and errors. |
| Sales orders | Shipment for sales orders starts in a different system to enable logistics balancing of third-party haulers, production of customs, and delivery documentation. This pushes the data to a major transport company. Upon picking or shipment of a sales order, the line details are the event that triggers the external system to analyze and determine the details of the utilized shipment. This pushing event depends on the ability for a business action to update the application. This could be that the order is picked and then the shipment information pushed to the application, or it is marked as shipped as it is pushed externally.  | This allows businesses with third-party transport companies to send shipping information to their vendors. This approach puts the responsibility of dispatch utilization on the external vendors and simplifies the setup. |
| Sales orders | Picking for sales orders can be performed in different systems, whether it’s a separate internal warehousing system or a third-party location that is not part of the application. Upon confirmation or picking of a sales order, the line details are the event that triggers the external system to analyze and determine the picking priority and utilization.  | This allows businesses with third-party warehouses to send the picking information to the system. This can also be used if the warehouse has automated picking machines that determine what is required. This approach puts the responsibility of prioritizing picking and utilization on the external system and simplifies the setup in the application. |
| Sales orders | Organizations are looking for ways to improve customer service, and to streamline and automate sales processes. These processes might involve several people, require many manual steps, or involve several third-party solutions. The email notification profile feature in Finance and Operations has limited email formatting capabilities. | By integrating with Microsoft Flow and creating business events for actions that are taken on sales orders, you can help improve the overall sales process, help increase customer satisfaction, and automate collaboration between sales and operations. |
| Batch processing | Scheduling batch jobs to process polling logic can put a lot of constraint on resources. To realize near real-time processing, it is compelling to schedule the batch to run as fast as it can in Finance and Operations, which typically ends up being every few minutes. These batch jobs are typically data import/export jobs that look for data to be processed. However, if data is not available the batch job processes empty cycles which can consume system resources.  | Using business events, the polling use case can be re-designed to be asynchronous if it is triggered by the business event. Data will be processed only when it is available. The business logic that makes the data available triggers the business event, which can then be used to start the data processing job/logic. This can save thousands of batch executions from running empty cycles and wasting system resources. |
| Production orders | The production scheduling process often relies on external systems or optimization engines to finalize the schedule. Automation of the process and an ability to integrate with external systems when a production order is scheduled can help increase productivity and decrease integration costs. | You can improve the integration and automation capabilities by creating a business event when a production order is scheduled. The information can be communicated to downstream systems, such as Microsoft Dynamics 365 Field Service for Internet of Things (IoT) data exchange, third-party manufacturing execution systems (MESs), or a scheduling optimization engine. |
| Production orders | Many organizations use third-party MESs to control and manage their machinery on the production floor. Integration with these systems is often complex. Additionally, communication between the production floor and the back office can be difficult. | By creating business events that are triggered when production orders are updated, you can help improve communications between the back office and the production floor. When integration is required with third-party systems for production, the business events can also be used to help simplify the integration process. |
| Case management | Case management is a platform feature that lets you track and manage various requests and issues that are internally or externally reported or requested. Typically, each type of case has a different process, and various contributors to the case might be involved throughout the case's lifecycle. The processes can be manual, and communication can often be delayed. Sometimes, contributors to the cases or stakeholders in them might not be users of the system. | By using Microsoft Flow when cases are updated, you can streamline and automate the business processes that are related to various case types. You can also automate communication and implement approval processes when necessary, depending on your organizational requirements. |
| Transportation management | Many organizations have separate and disconnected systems for managing transportation. Additionally, the staff that is responsible for arranging transportation is typically not the same staff that creates and confirms orders, or the same staff that carries out the work to ship or receive orders. This situation can lead to a breakdown or lack of communication, and can require manual processes to notify various departments when an order is ready for the next step in the process. In many cases, third-party shipping software is used, and data is entered into many systems or tracked in paper logs. | By using business events together with Microsoft Flow, you can streamline the overall transportation management process and help improve communications between departments. |