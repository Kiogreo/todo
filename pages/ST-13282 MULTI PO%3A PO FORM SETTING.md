# Acceptance Criteria
	- Form Setting Splitting
	  logseq.order-list-type:: number
		- **Global PO Form Setting** page = The current `Purchase Order: Purchase Orders Settings` page
		- **Individual PO Form Setting** page = The page after user clicked on the `More Settings` from the `Purchase Order: Purchase Orders Settings` page
	- Reorganise PO Settings
	  logseq.order-list-type:: number
		-
- # Task Breakdown
	- ## Company & Form Setting Setup
		- #re-test **Hub/ADAM features page**
		  collapsed:: true
			- TODO #q&a Do we still need to add setting in HUB?
				- We already implemented the feature flag without using HUB at the moment
			- TODO #q&a What does it mean by this statement? **"Create new PO form setting (for switchover)"**
		- #re-test **Role & Permissions**
		  collapsed:: true
			- TODO #q&a The **"remain the same"** here means that all single PO's existing permission applies to multi PO, right?
		- #re-test **User Form Assignment**
		  collapsed:: true
			- TODO we already implemented this in existing Multi PO & Single PO
		-
	- ## Form Setting Splitting
		- ### Global PO Form Setting
		  collapsed:: true
			- From ticket`Context` section:
				- ```
				  Context:
				  Previous understanding was that within a company, only ONE template for PO is ever used
				  
				  However, from our understanding, for GROUPs, each company may have a different PO template. Also, within a single company, there can be multiple PO types.
				  
				  For Lembaga Zakat Selangor, different PO types also have different approvals as some POs require management approvals, and others which have been pre-approved, can just be departmental approval
				  ```
					- TODO #q&a What does **"for GROUPs"** here is referring to?
					- TODO #q&a what does it mean by **PO Template**?
			-
		- ### Individual PO Form Setting
		  collapsed:: true
			- #re-test **PR** or **RFX** Form Settings can be routed to the different **PO** Form Settings
			  collapsed:: true
				- PR
					- Manual PR -> PO
					- Auto PR -> PO
				- RFX
					- RQ > RFX > PR
					  id:: 695e10f2-48e5-49a3-8576-d02f932e6884
					- PR > RFX > PO
			- #re-test Each PO will have GR & IR form attached
			  collapsed:: true
				- DONE #q&a We should add the `Form Name` column within both `Good Received (GR)` & `Purchase Invoice (PI) (PI)` similar to the `My Purchase Orders` & `Company Purchase Order` listing page
				  collapsed:: true
					- DONE If yes, then  Export Submission CSV should also be affected since we need to add a new column
					- DONE Seems like `PI` listing page does not have CSV export
				- DONE #q&a This will affect the search query within `GR` & `PI` listing page?
				- DONE #q&a Do we need to add filter dropdown for PO Form Setting within  `GR` & `PI` listing page?
				- DONE #q&a We should also apply the same thing within `Good Returns (GRN)` listing page including the filter & search function?
			- #re-test Each PO form can be revised or **issued** and sent to a different approval flow
			  collapsed:: true
				- TODO #q&a Does the word `issued` here are synonymous to `created` PO?
			- #re-test Create new Form
			  collapsed:: true
				- Type of PO form
			- #re-test History Logs
			  collapsed:: true
				- Form Creation
				- Form Deletion
				- Form Name Change
				- Form Details change
		-
	- ## Reorganise PO Settings
		- ### Form Listing Page
			- #re-test **Form listing Page** (deployed during Phase 1 of Multi PO)
			  collapsed:: true
				- TODO Create new Form
				- TODO History Logs
				  collapsed:: true
					- Form Creation
					  id:: 695e0094-fb6e-4486-b9f4-6fb715536c16
					- Form Deletion
					- Form Name Change
					- Form Details change
		- ### Global PO Form Setting
			- #re-test Internal Source
			  collapsed:: true
				- TODO figure out how it work in BE
			- collapsed:: true
			  
			  PO Acceptance
				- TODO #q&a Is this referring to a scenario where vendor is accepted?
			- collapsed:: true
			  
			  Enable Requestor to access PO Details
				- TODO #q&a I guess it means that the user (in this case, I assume its the original submitter for RQ/PR/PO?) who created RQ should be able to access PO details even without **LOGIN-IN** in 1s?
			- #re-test Revise & Edit PO
			  collapsed:: true
				- TODO Enable Revise PO
				- TODO Require Approval for Lower Revision Sum
				- TODO Enable Revise on POs that have GR activity on them
				- DOING Enable Edit PO
				  :LOGBOOK:
				  CLOCK: [2026-01-07 Wed 16:07:55]
				  :END:
			- #re-test Company PO Page filters
			  collapsed:: true
				- TODO check again with both @sim & @ben since we've implemented Filtering for `Form Name`
			- #re-test Closing Po
			  collapsed:: true
				- TODO Enable Goods Received Closing
				- TODO Enable Extra Receiving Quantity
				- TODO Enable FOC Quantities
				- TODO Enable Invoice Received Closing
				- TODO Enable Receiving Invoice Price Update
				- TODO Enable Goods Return
			- collapsed:: true
			  
			  Advance Payment
				- TODO create mailing group
				- TODO check advance payment flow
			- collapsed:: true
			  
			  EVA settings
				- TODO Notify Users when Vendor Uploads GR attachment
				- TODO Notify Users when Vendor Uploads Invoice
		- ### Individual PO Form Setting
			-