## Acceptance Criteria
	- ### Split current PO Form Setting in **Global** & **Individual** PO Form Setting.
		- **Global PO Form Setting** page = The current `Purchase Order: Purchase Orders Settings` page
		- **Individual PO Form Setting** page = The page after user clicked on the `More Settings` from the `Purchase Order: Purchase Orders Settings` page
		-
	- ### Global PO Form Setting
		-
	- ### Individual PO Form Setting
		- **PR** or **RFX** Form Settings can be routed to the different **PO** Form Settings
			- #### PR
			  id:: 695dd758-64a5-4891-907c-362e5c70611d
				- In PR Form Setting, if `Internal Source` is enabled & `Source Modules` link to
			- #### RFX
				-
		- Each PO will have GR & IR form attached
			- DONE We should add the `Form Name` column within both `Good Received (GR)` & `Purchase Invoice (PI) (PI)` similar to the `My Purchase Orders` & `Company Purchase Order` listing page
				- DONE If yes, then  Export Submission CSV should also be affected since we need to add a new column
				- DONE Seems like `PI` listing page does not have CSV export
			- DONE This will affect the search query within `GR` & `PI` listing page?
			- DONE Do we need to add filter dropdown for PO Form Setting within  `GR` & `PI` listing page?
			- DONE We should also apply the same thing within `Good Returns (GRN)` listing page including the filter & search function?
		- Each PO form can be revised or **issued** and sent to a different approval flow
			- TODO Does the word `issued` here are synonymous to `created` PO?
	- ### Setup Setting
		- **Hub/ADAM features page**
			- TODO Do we still need to add setting in HUB?
				- We already implemented the feature flag without using HUB at the moment
			- TODO What does it mean by this statement? **"Create new PO form setting (for switchover)"**
		- Role & Permissions
			- TODO The **"remain the same"** here means that all single PO's existing permission applies to multi PO, right?
		- TODO User Form Assignment (we already implemented this in existing Multi PO & Single PO)
			- So, should be no issue
	- ### Reorganise PO Settings
		- ### Global setting page
			- Internal Source
				- TODO figure out howit work in BE
			- PO Acceptance
				- TODO Is this referring to a scenario where vendor is accepted?
			- Enable Requestor to access PO Details
				- TODO I guess it means that the user (in this case, I assume its the original submitter for RQ/PR/PO?) who created RQ should be able to access PO details even without **LOGIN-IN** in 1s?
			- Revise & Edit PO
				- TODO confirm back the flow for both **REVISE**
				- Current test cases
					-
			- Company PO Page filters
			- Closing Po
			- Advance Payment
			- EVA settings
			- (More Settings) button leads to **Form listing Page**
		- ### Individual setting  page
			- Create new Form
				- Type of PO form
			- History Logs
				- Form Creation
				- Form Deletion
				- Form Name Change
				- Form Details change
- ## Q&A
	- TODO From ticket`Context` section:
		- ```
		  Context:
		  Previous understanding was that within a company, only ONE template for PO is ever used
		  
		  However, from our understanding, for GROUPs, each company may have a different PO template. Also, within a single company, there can be multiple PO types.
		  
		  For Lembaga Zakat Selangor, different PO types also have different approvals as some POs require management approvals, and others which have been pre-approved, can just be departmental approval
		  ```
			- TODO What does **"for GROUPs"** here is referring to?
			- TODO what does it mean by **PO Template**?
			-
			-