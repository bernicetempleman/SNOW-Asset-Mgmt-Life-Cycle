# SNOW-Asset-Mgmt-Life-Cycle

## What is an Asset:
- An asset is an item, entity, or thing (tangible or intangible) that 
holds value for a Company or a person.
- Examples of Assets are Estates, Resources, Inventory, Equipment 
and Valuables.
- Note: All CI’s is not an asset, but all Asset’s is a CI.

## Asset Management System:
- It is an accounting process that seeks to track fixed assets for the 
purpose of financial accounting, preventive maintenance and 
avoid thefts.
- Organizations faces a significant challenge to track the location, 
quantity, condition, maintenance, and depreciation status of their 
fixed assets
- AMS gives the best way to manage the physical movement of 
asset like how many assets are there in the store, how many 
assets are assigned to employee and where the asset is lying 
physically with the help of bar code scanning.

## Asset Management vs CMDB
- Note: Asset Management and Configuration Management 
Database are related to each other but have different goals.
- Asset management focuses on the financial tracking of the 
company property. 
- Configuration Management focused on building and maintaining 
elements that creates an available network of services.

## Asset Management Lifecycle:
![image](https://user-images.githubusercontent.com/12488769/148689079-a2a412ee-2fad-474e-942d-ec2fb904210a.png)

![image](https://user-images.githubusercontent.com/12488769/148689090-b2b79622-9bdb-44a4-9bf9-5e05b61daefa.png)


## Benefits of Asset Management:
- Keep a track of all assets / Control inventory that is 
purchased and used.
- Reduce the cost of purchasing and managing assets.
- Manage assets from different locations.
- Provide an opportunity to plan against financial, operational,
and legal risk.
- Define the service levels.
- Organize the Asset Portfolio.
- Create a more efficient operation with ability to track 
performance.
- Improve Time Management.
- Measure and monitor life cycle cost from Planning to 
Disposal.
- Promote the economic stability and growth of your 
company.
![image](https://user-images.githubusercontent.com/12488769/148689110-3c5e8c02-44d9-4a22-98ee-6fa284ee2677.png)

## Asset State and Substate:
![image](https://user-images.githubusercontent.com/12488769/148689116-26c24be9-b2f9-4edb-bd33-b11b8441dcd8.png)


## ServiceNow includes default States and Substates that meet the 
needs of most customers:
- On Order – the asset has been ordered but has not yet been 
received.
- In Stock – the asset is in Stockroom. Its Substates indicate 
whether an in-stock asset is available to be deployed or not.
- In Transit – the asset is being transferred from one location 
to another (ex: between stockrooms).
- In Use – a non-consumable is being used; the asset is 
typically managed as a Configuration Item as this state.
- Consumed – a consumable is being used.
- In Maintenance - the asset is being maintained.
- Retired – indicates end of life.
- Missing – the asset cannot be located after the appropriate 
level of Investigation has been performed.

## Asset and CI Process:
![image](https://user-images.githubusercontent.com/12488769/148689127-b6ae46f5-1863-4a93-a692-55da2c046585.png)

## Ensure the following plugins are active and load demo 
data if available.
- Contract Management
- Procurement
- Data Certification
- Managed Documents
- Extended CMDB
- My Assets
- Cost Management
- Hardware Asset Management (Paid plugin)

## 1. Create a New Hardware model under Product Catalog Application, with the following attributes:
- Manufacturer “Lenovo”
- Name “G950”
- Display Name “Lenovo G950”
- Model Categories “Computer”
- Asset Tracking Strategy “Leave to Category”
- Cost “10000 $”
- Model Number “G950-543”
- Status “In Production”
-  Expenditure type “Capex”

## 2) Publish a Model to the Hardware Catalog (Using Related Link – Publish to Hardware Catalog)

## 3) Click on the Product Catalog Tab and it should show you the Catalog Item named as “G950”.

## 4) Open the Catalog Item and click on Try it to submit the item with 10 quantities and it should give you the Request number.

## 5) Once Vendor starts the delivery, we need to keep it in the Stockroom. So, lets create the Stockroom first.
### a In the Inventory application → Stockrooms → Create New
- Name: ServiceNow Helpdesk Stockroom
- Assignment Group – Take any one
- Location: Select specific location “APAC → India → Hyderabad -> 18 iLabs xxxxxxx”
- Type – Warehouse
- Manager – Select anyone

### b. Once submitted, you can see the empty Stockroom with no Hardware, no Consumables, no Software Licenses, and no Other Assets.

## 6) Goto Requests under Procurement application and then Open the Request created on Step no. 4. Sourced Checkbox should be unchecked because still Purchase Order has not been created yet, and it should be Pending for Approval as well.

## 7) Approve the Request to create the Catalog Task with Short Description as ‘Source Request Items’.

## 8) Open the Task and Click on Source Request button on the Top.

## 9) Now we need to Add Purchase Order
- Select Vendor as “Lenovo”
-  Quantity would automatically come to 10
-  Destination Stockroom – ServiceNow Stockroom Helpdesk
-  Click on Submit
-  Purchase Order has been created with PO number in the Request.

## 10) Open the PO generated and check the details. It should be in Requested state because it has not been Ordered yet.
There should be one Purchase Line Items with State as Requested as well.

## 11) Click on Order and Status will be ordered now for PO and Purchase Order Line items.

## 12) Now open the Purchase Line items to create Hardware Asset Prior to Delivery (Click on Related Link). Based on the quantity ordered, it will add the same number of Assets.

## 13) We need to add Asset tags and Serial number now for all Assets.
For ex: TAG001 and Serial number: 123456 (Repeat the same for all 10 assets with different Tags)

## 14) Go back to the Purchase Order and check the status should be changed to “Pending Delivery”

## 15) All the Assets below in the Related Link, should be in “Order” state. Open any Asset and check the details of the Asset and Related list “Expense Line”

## 16) Go back to the Purchase Order and click on Receive button on the top.
- Let’s say we receive only 5 Assets as of now and 5 is still Pending to Receive. Update Receiving Quantity to ‘5’ and click on submit.
- Now check the 5 Assets states should be ‘In Stock’ with Substate as ‘Available’ and other 5 Asset state should be still in ‘On Order’
- Now we need to update the Invoice accordingly for the Received Asset.

## 17) On the Purchase Order form, you would see ‘Receiving Slips’ Related Link which will be your Invoice number.

## 18) Goto Assets and check the Hardware Assets now. Open any one Asset. Now we need to do the installation of the Software and other details before we handover to the Employee. So, change the Sub State to ‘Pending install’ now and add Comments & Department.

## 19) Once all the installations are done, we will change the Substate to ‘Available’ again.

## 20) Now we need to assign this Asset to someone in the organization. So, lets change the State to ‘In Use’ and Assigned to ‘Your User ID’. Add the Installed Date as well.

## 21) Now let’s go through the Financial Details under the ‘Financial’ Form section and update the Invoice number as ‘INV001’

## 22) Next let’s go through ‘Depreciation’ Form Section.
a. Select Depreciation as ‘SL 3 years’
b. Depreciation Effective Date: As per the Government policy it should be same date when Asset was handed over to Employee. But for testing purpose, let’s put some older date to calculate the Depreciation (Using the Related Link – Calculate Depreciation)

## 23) Now let’s go to ‘Contracts’ Form Section.
a. Warranty Expiration – Select any date of 2022.
b. Support Group – Select any Group (who will provide the Support for any kind of issue)

## 24) Let’s say now Employee has some issue in the Asset, so he/she returns it back to Asset Team. So, change back to State to ‘In Stock’

## 25) Since we have received back the Asset, so we will be checking the Stock Inventory now. Goto Stockroom and track all Assets.

## 26) We can also add the consumables to the Stockroom (if required)
-  Click on New and add Consumables to the Stockroom
-  Model Category: Monitor
-  Model: Samsung SyncMaster 22” Class BackLight LED
-  Quantity: 30
-  State: In Stock
-  Stockroom: ServiceNow Helpdesk Stockroom
-  Click on Submit.
-  Open the Consumable and Click on Consume button on the Top. Select Quantity as 2, select any Asset and add any User who would be consuming the same.
-  Once you give it to the User, Quantity should Auto change to 28.

## 27) Open the same Asset tag now and check the Consumables in the ‘Asset’ Related Link. (This is same as like
you are providing Headphone with the Laptop to the Employee)

## 28) Now let’s say I need to Transfer the Asset from One Stockroom to another Stockroom. For that, I need to create Transfer Order. (Prerequisite for creating Transfer Order is Asset state should be in ‘In Stock’)
### Under the Inventory, Create Transfer Order:
-  From StockRoom
-  New StockRoom
-  Delivery by date (Expected delivery date)
-  Click on Submit
### Open the Transfer Order and Create Transfer Order Lines from the Related List below:
-  Model: Computer
-  Asset: Select the Asset you want to Transfer
-  Click on Submit
### Once the Transfer Order Line is created, it will generate multiple Task one by one. Close all the Tasks sequentially and check the Stage of the Transfer Order Line at every closure of the Task.
### Once it is delivered, please check the Asset should be Tagged to the Target Stockroom.

## 29) Final step, change the Asset state to ‘In maintenance’ if you want to send the Asset to Vendor for Maintenance or change the state to ‘Retired’ if you want to Dispose the Asset.
![image](https://user-images.githubusercontent.com/12488769/147889769-aa0a3cc0-04a2-4e40-8875-c6570ed215d2.png)
