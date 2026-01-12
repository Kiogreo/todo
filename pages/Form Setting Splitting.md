# Task Brakedown
	- ### Global PO Form Setting {{renderer :todomaster}}
		- TODO retest global PO form setting that was not split & ensure they're still working as is
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
		- #re-test **PR** or **RFX** Form Settings can be routed to the different **PO** Form Settings
			- **PR**
				- TODO `Manual PR -> PO`
				- TODO `Auto PR -> PO`
			- **RFX**
				- TODO `RQ > RFX > PR`
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
-