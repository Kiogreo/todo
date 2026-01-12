# Task Breakdown
	- ### Global PO Form Setting {{renderer :todomaster}}
		- TODO Re-test internal Source
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
	- ### Form Listing Page {{renderer :todomaster}}
	  collapsed:: true
		- #re-test Form listing Page (deployed during Phase 1 of Multi PO)
			- TODO Create new Form
			- TODO History Logs
				- Form Creation
				- Form Deletion
				- Form Name Change
				- Form Details change
			- ![Screenshot 2026-01-07 at 4.40.36 PM.png](../assets/Screenshot_2026-01-07_at_4.40.36 PM_1767775241702_0.png){:height 269, :width 718}
	- ### Individual PO Form Setting {{renderer :todomaster}}
	  collapsed:: true
		- Form Setting Tab
		  collapsed:: true
			- Move the below fields from ((695df31d-f53a-450c-8235-f4a73fe16036)) into ((695e0e27-9809-42ad-9a50-64e67dc9a2db))
			- TODO Auto PO
				- ![image.png](../assets/image_1767851079463_0.png)
				- Setting key
					- | **FIELD** | **KEY** | **REMARKS** |
					  | --- | --- | --- |
					  | Enable auto-generate PO from PR | `purchase_requisition_enable_auto_generate_po_from_pr` | |
					  | Enable Auto-split | `purchase_requisition_enable_auto_split_po_from_pr` | |
			- TODO Auto PO Email
				- ![image.png](../assets/image_1767851132776_0.png)
				- Setting key
					- | **FIELD** | **KEY** | **REMARKS** |
					  | --- | --- | --- |
					  | Auto Email POs created manually` | `purchase_order_enable_auto_email_auto_po` | |
					  | Send a copy to submitter | `` | |
					  | Send a copy to requestor | `` | |
					  | Auto Email PO generated via Auto PO for the following PR forms | `` | |
					  | Send a copy to submitter | `` | |
					  | Send a copy to requestor | `` | |
				- Note
					- Add item from approved origin
					- Display assigned vendor
						-
			- TODO PO T&C
				- ![image.png](../assets/image_1767851154836_0.png)
				- Setting key
					- | **FIELD** | **KEY** | **REMARKS** |
					  | --- | --- | --- |
					  | PDF Terms & Conditions | `purchase_requisition_tncdd                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             aaa                                                                                                                                                                                                                         dcvaďðdcx` | |
			- TODO PO Email Text
				- ![image.png](../assets/image_1767851187113_0.png)
				- Setting key
					- | **FIELD** | **KEY** | **REMARKS** |
					  | --- | --- | --- |
					  | Send a copy to submitter | `` | |
					  | Send a copy to requestor | `` | |
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