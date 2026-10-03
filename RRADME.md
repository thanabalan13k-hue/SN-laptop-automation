# Streamlining IT Procurement: Automating Standard Laptop Procurement

A ServiceNow project (Naan Mudhalvan / Skillwallet) that automates the standard laptop procurement process using **Flow Designer**.

## Overview
When a user orders a **Standard Laptop** from the Service Catalog, the request goes through approval. Once it is approved, a flow automatically creates a **Catalog Task** for the Requested Item and assigns it to the **Hardware** group for laptop configuration.

This removes manual task creation, reduces delays and human errors, and makes sure approved requests are never missed.

## Technologies Used
- ServiceNow (Personal Developer Instance)
- Service Catalog
- Flow Designer
- Requested Items, Approvals and Catalog Tasks

## Project Structure
| Milestone | Description |
|-----------|-------------|
| 1. Flow | Create the **Standard laptop task** flow with a Service Catalog trigger and a Create Catalog Task action |
| 2. Flow assignment | Attach the flow to the Standard Laptop item under Process Engine in Maintain Items |
| 3. Service Catalog | Order the laptop, approve the request, and verify the catalog task |

## Implementation Steps
### 1. Create the Flow
1. Open **Flow Designer** and create a new Flow named `Standard laptop task` (Application: Global, Run as: System User).
2. Add the trigger **Service Catalog**.
3. Add the action **Create Catalog Task** and drag the Requested Item into the Request item field.
4. Set the field values:
   - Short description: `Laptop need to Configured`
   - Description: `Laptop need to Configured`
   - Assignment group: `Hardware`
   - Approval: `Approved`
5. Save and **Activate** the flow.

### 2. Assign the Flow to the Catalog Item
1. Go to **Maintain Items** and open **Standard Laptop**.
2. Open the **Process Engine** tab, remove existing automations, and select the flow `Standard laptop task`.
3. Save the record.

### 3. Test the Flow
1. Open **Service Catalog > Hardware > Standard Laptop** and click **Order Now**.
2. Open the Request (REQ...) and approve it from the **Approvers** tab.
3. Open the Requested Item (RITM...) and scroll to **Catalog Tasks**.
4. Open the Catalog Task (SCTASK...) and confirm the short description and the Hardware assignment group.

## Result
After approval, a Catalog Task is created automatically with the short description `Laptop need to Configured` and is assigned to the **Hardware** group.

## Screenshots

### 1. Flow – Standard laptop task
<!-- screenshots/01-flow.png -->


![Flow](screenshots/01-flow.png)



### 2. Process Engine tab (Standard Laptop item)


![Process Engine](screenshots/02-process-engine.png)



### 3. Approved request (REQ)


![Approved Request](screenshots/03-approved-request.png)



### 4. Catalog Task created (SCTASK)


![Catalog Task](screenshots/04-catalog-task.png)

## Team
- Dhanabalan M (Team Lead)

## Conclusion
The Standard Laptop Procurement Automation project shows how ServiceNow Flow Designer can streamline a common IT procurement process, reducing manual work and errors.
