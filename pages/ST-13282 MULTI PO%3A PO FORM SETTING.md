# Reminders
	- #meeting PO Form Setting: Item Setting Re-organisation
	  id:: 69644daa-4699-4996-85a4-9daa3d45a2f9
	  :LOGBOOK:
	  CLOCK: [2026-01-12 Mon 09:33:44]--[2026-01-12 Mon 09:34:00] =>  00:00:16
	  CLOCK: [2026-01-12 Mon 09:34:01]--[2026-01-12 Mon 09:34:32] =>  00:00:31
	  CLOCK: [2026-01-12 Mon 09:34:33]
	  :END:
		- Objective
			- Discuss & finalize the item setting reorganisation stated in the `Item Information Part2` section of https://supplycart.atlassian.net/browse/ST-13282
		- Current Status
			- We want to change the `Item Configuration` sub-section from:
				- ![image.png](../assets/image_1768188937302_0.png){:height 424, :width 462}
			- To the below:
				- Enable add FFT
				- Enable add catalogue products
					-
- # Acceptance Criteria
  collapsed:: true
	- [[Form Setting Splitting]]
	  logseq.order-list-type:: number
		- **Global PO Form Setting** page = The current `Purchase Order: Purchase Orders Settings` page
		- **Individual PO Form Setting** page = The page after user clicked on the `More Settings` from the `Purchase Order: Purchase Orders Settings` page
	- [[Reorganise PO Settings]]
	  logseq.order-list-type:: number
		- Some fields from **Global PO Form Setting** will be moved into **Individual PO Form Setting**
		  logseq.order-list-type:: number
- ## Q&A
  collapsed:: true
	- What is the main difference between Global PO Setting & Individual PO Setting?
	  collapsed:: true
		- | Global PO Setting | Individual PO Setting |
		  | --- | ---- |
		  | Feature toggle will affect existing PO (live change) | Feature toggle will only affect newly drafted PO |
		  | Changes will be set under global Company Setting | Changes will be set under PO Form Setting |
	- For the `enable requestor to access PO Details page` setting, do we still use this? If yes, can anyone help me to understand how it works?
	  collapsed:: true
		- Yes, the user access the PO details page from the reference in PR details page
			- @nadzmi Need to check whether user can actually view the page once redirected to there'
			- Can remove first `Enable Requestor to access PO Details` & see what modules are affected
	- Po acceptance not needed to split
- # Task Breakdown
	- ## [[Company & Form Setting Setup]] {{renderer :todomaster}}
	  collapsed:: true
		- #re-test **Hub/ADAM features page**
		  collapsed:: true
			- DONE #q&a Do we still need to add setting in HUB?
				- We already implemented the feature flag without using HUB at the moment
			- DONE #q&a What does it mean by this statement? **"Create new PO form setting (for switchover)"**
				- A: `switchover` here means when we switch from partial Multi PO implementation into full Multi PO implementation throughout **ADAM**
		- #re-test **Role & Permissions**
		  collapsed:: true
			- DONE #q&a The **"remain the same"** here means that all single PO's exis``ting permission applies to multi PO, right?
			  collapsed:: true
				- A: the **Remain the same** statement under the **Roles & Permissions** means that all Multi PO’s permission shares the same permission as existing Single PO
		- #re-test **User Form Assignment**
		  collapsed:: true
			- DONE we already implemented this in existing Multi PO & Single PO
	- ## [[Form Setting Splitting]] {{renderer :todomaster}}
	  collapsed:: true
		- ### Global PO Form Setting
		  collapsed:: true
			- #q&a From ticket `Context` section:
				- DONE What does **"for GROUPs"** & **PO Template** refers to?
				- ```
				  Context:
				  Previous understanding was that within a company, only ONE template for PO is ever used
				  
				  However, from our understanding, for GROUPs, each company may have a different PO template. Also, within a single company, there can be multiple PO types.
				  
				  For Lembaga Zakat Selangor, different PO types also have different approvals as some POs require management approvals, and others which have been pre-approved, can just be departmental approval
				  ```
				- A: Group here means that multi po will help in terms of making single po form setting to encapsulate different groups of companies' needs
		- ### Individual PO Form Setting
		  collapsed:: true
			- #re-test **PR** or **RFX** Form Settings can be routed to the different **PO** Form Settings
				- **PR**
					- TODO `Manual PR -> PO`
					- TODO `Auto PR -> PO`
				- **RFX**
					- TODO `RQ > RFX > PR`
					  id:: 695e10f2-48e5-49a3-8576-d02f932e6884
					- TODO `PR > RFX > PO`
			- #re-test Each PO will have GR & IR form attached
				- Answer to all the below questions:
					- it's not needed to add `Form Name` column for GR, RTN & PI moduel.
				- DONE #q&a We should add the `Form Name` column within both `Good Received (GR)` & `Purchase Invoice (PI) (PI)` similar to the `My Purchase Orders` & `Company Purchase Order` listing page
					- DONE If yes, then  Export Submission CSV should also be affected since we need to add a new column
					- DONE Seems like `PI` listing page does not have CSV export
				- DONE #q&a This will affect the search query within `GR` & `PI` listing page?
				- DONE #q&a Do we need to add filter dropdown for PO Form Setting within  `GR` & `PI` listing page?
				- DONE #q&a We should also apply the same thing within `Good Returns (GRN)` listing page including the filter & search function?
			- #re-test Each PO form can be revised or **issued** and sent to a different approval flow
				- DONE #q&a Does the word `issued` here are synonymous to `created` PO?
			- #re-test Create new Form
				- Type of PO form
			- #re-test History Logs
				- Form Creation
				- Form Deletion
				- Form Name Change
				- Form Details change
	- ## [[Reorganise PO Settings]] {{renderer :todomaster}}
		- ### Global PO Form Setting
		  id:: 695df31d-f53a-450c-8235-f4a73fe16036
		  collapsed:: true
			- #re-test Internal Source
			  collapsed:: true
				- DONE figure out how it work in BE
			- collapsed:: true
			  
			  PO Acceptance
				- DONE #q&a Is this referring to a scenario where vendor is accepted?
					- **Answer** yes
				- DONE #tanya-ben For the “PO Acceptance“ feature, do we not need to separate them into it’s own individual PO setting?
					- **Answer** NO
			- collapsed:: true
			  
			  Enable Requestor to access PO Details
				- DONE #q&a #tanya-ben Is this still used?
					- **Answer**
						- Yes, still used.
						- From PR details page, requester will access PO details page through the internal source reference.
			- #re-test Revise & Edit PO
				- DONE Enable Revise PO
				- DONE Require Approval for Lower Revision Sum
					- **Revision Sum** = total item cost
					- By default all revise PO that has higher **Revision Sum** require approval
				- TODO Enable Revise on POs that have GR activity on them
					- How does it work?
				- DOING Enable Edit PO
				  :LOGBOOK:
				  CLOCK: [2026-01-07 Wed 16:07:55]
				  :END:
			- #re-test Company PO Page filters
				- DONE check again with both @sim & @ben since we've implemented Filtering for `Form Name`
			- #re-test Closing Po
				- DONE Enable Goods Received Closing
				- DONE Enable Extra Receiving Quantity
				  collapsed:: true
					- | Toggle | Screenshot |
					  | --- | --- |
					  | **Enabled** | ![Screenshot 2026-01-08 at 11.41.56 AM.png](../assets/Screenshot_2026-01-08_at_11.41.56 AM_1767843745201_0.png){:height 254, :width 531} |
					  | **Disabled** | ![Screenshot 2026-01-08 at 11.44.09 AM.png](../assets/Screenshot_2026-01-08_at_11.44.09 AM_1767843900502_0.png){:height 168, :width 536} |
				- DONE Enable FOC Quantities
				  collapsed:: true
					- | Toggle | Screenshot |
					  | --- | --- |
					  | **Enabled** | ![image.png](../assets/image_1767844171099_0.png) |
					  | **Disabled** | ![image.png](../assets/image_1767844255138_0.png) |
				- DONE Enable Invoice Received Closing
				  collapsed:: true
					- | Toggle | Screenshot |
					  | --- | --- |
					  | **Enabled** | ![image.png](../assets/image_1767849912691_0.png) |
					  | **Disabled** | ![image.png](../assets/image_1767849829983_0.png) |
				- TODO Enable Receiving Invoice Price Update
				- TODO Enable Goods Return
			- Advance Payment
				- TODO create mailing group
				- TODO check advance payment flow
			- EVA settings
				- TODO Notify Users when Vendor Uploads GR attachment
				- TODO Notify Users when Vendor Uploads Invoice
		- ### Form Listing Page
		  collapsed:: true
			- #re-test Form listing Page (deployed during Phase 1 of Multi PO)
				- TODO Create new Form
				- TODO History Logs
					- Form Creation
					  id:: 695e0094-fb6e-4486-b9f4-6fb715536c16
					- Form Deletion
					- Form Name Change
					- Form Details change
				- ![Screenshot 2026-01-07 at 4.40.36 PM.png](../assets/Screenshot_2026-01-07_at_4.40.36 PM_1767775241702_0.png){:height 269, :width 718}
		- ### Individual PO Form Setting
		  id:: 695e0e27-9809-42ad-9a50-64e67dc9a2db
			- Form Setting Tab
				- Move the below fields from ((695df31d-f53a-450c-8235-f4a73fe16036)) into ((695e0e27-9809-42ad-9a50-64e67dc9a2db))
				- TODO Auto PO
					- ![Screenshot 2026-01-12 at 12.06.55 PM.png](../assets/Screenshot_2026-01-12_at_12.06.55 PM_1768190844059_0.png)
					- Setting key
					  id:: 695f4504-b56d-4123-9f41-8de373c2c547
						- id:: 695f450e-dd00-47d5-811b-1a042eeed348
						  | **FIELD** | **KEY** | **REMARKS** |
						  | --- | --- | --- |
						  | Enable auto-generate PO from PR | `purchase_requisition_enable_auto_generate_po_from_pr` | |
						  | Enable Auto-split | `purchase_requisition_enable_auto_split_po_from_pr` | |
				- TODO Auto PO Email
					- ![Screenshot 2026-01-12 at 12.09.02 PM.png](../assets/Screenshot_2026-01-12_at_12.09.02 PM_1768190954602_0.png)
					- Setting key
						- | **FIELD** | **KEY** | **REMARKS** |
						  | --- | --- | --- |
						  | Enable auto PO email | `purchase_order_enable_auto_po` | This setting is not shown in UI |
						  | Auto Email POs created manually` | `purchase_order_enable_auto_email_auto_po` | |
						  | Send a copy to submitter | `purchase_order_auto_email_po_send_to_submitter` | |
						  | Send a copy to requestor | `purchase_order_auto_email_auto_po_send_to_requestor` | |
						  | Auto Email PO generated via Auto PO for the following PR forms | `purchase_order_enable_auto_email_auto_po`, `purchase_order_enable_auto_email_auto_po_forms` | |
						  | Send a copy to submitter | `purchase_order_auto_email_po_send_to_submitter` | |
						  | Send a copy to requestor | `purchase_order_auto_email_po_send_to_requestor` | |
					- Note
						- Add item from approved origin
						- Display assigned vendor
							-
				- TODO PO T&C
					- ![Screenshot 2026-01-12 at 12.10.18 PM.png](../assets/Screenshot_2026-01-12_at_12.10.18 PM_1768191030384_0.png)
					- ![Screenshot 2026-01-12 at 12.12.19 PM.png](../assets/Screenshot_2026-01-12_at_12.12.19 PM_1768191153918_0.png)
					- Setting key
						- | **FIELD** | **KEY** | **REMARKS** |
						  | --- | --- | --- |
						  | PDF Terms & Conditionsc | `purchase_requisition_tnc` | |
				- TODO PO Email Text
					- ![Screenshot 2026-01-12 at 12.10.53 PM.png](../assets/Screenshot_2026-01-12_at_12.10.53 PM_1768191065280_0.png)
					- ![Screenshot 2026-01-12 at 12.11.51 PM.png](../assets/Screenshot_2026-01-12_at_12.11.51 PM_1768191123450_0.png)
					- Setting key
						- | **FIELD** | **KEY** | **REMARKS** |
						  | --- | --- | --- |
						  | Send a copy to submitter | `purchase_order_email_default_send_to_submitter` | |
						  | Send a copy to requestor | `purchase_order_email_default_send_to_` | |
			- #re-test Form Fields Tab
				- Part 1
					- #re-test Delivery Information
					- #re-test Vendor Information
					- #re-test Submission Information
					- #re-test Item information
					- Relabel Budget Setting (**Check JIRA Epic**)
						- Limit value based
							- add toggle to enable/disable
				- Part 2 - Item configuration
					- Plan = split up all the grouped settings into each individual settings into modular
						- **KIV** from @ben in what are the setting that we want to
			- #re-test PO PDF Tab
			- #re-test Setup Logs