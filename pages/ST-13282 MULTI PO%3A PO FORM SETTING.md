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
			- TODO We should add the `Form Name` column within both `Good Received (GR)` & `Purchase Invoice (PI) (PI)` similar to the `My Purchase Orders` & `Company Purchase Order` listing page
				- TODO If yes, then  Export Submission CSV should also be affected since we need to add a new column
				- TODO Seems like `PI` listing page does not have CSV export
			- TODO This will affect the search query within `GR` & `PI` listing page?
			- TODO Do we need to add filter dropdown for PO Form Setting within  `GR` & `PI` listing page?
			- TODO We should also apply the same thing within `Good Returns (GRN)` listing page including the filter & search function?
		- Each PO form can be revised or **issued** and sent to a different approval flow
			- TODO Does the word `issued` here are synonymous to `created` PO?
			-
- ## Q&A
	- TODO From ticket`Context` section:
		- ```
		  Context:
		  Previous understanding was that within a company, only ONE template for PO is ever used
		  
		  However, from our understanding, for GROUPs, each company may have a different PO template. Also, within a single company, there can be multiple PO types.
		  
		  For Lembaga Zakat Selangor, different PO types also have different approvals as some POs require management approvals, and others which have been pre-approved, can just be departmental approval
		  ```
			- TODO What does **"for GROUPs"** here is referring to?
			-
			-