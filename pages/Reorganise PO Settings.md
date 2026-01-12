# Task Breakdown
	- ### Global PO Form Setting {{renderer :todomaster}}
		- TODO Re-test Internal Source is still working from 1 form to another
		- TODO Re-test PO Acceptance
		- Enable Requestor to access PO Details
			- TODO for now, we can try to remove the settings & see if it affects the existing system
		- Revise & Edit PO
			- TODO Enable Revise PO
			- TODO Require Approval for Lower Revision Sum
			- TODO Enable Revise on POs that have GR activity on them
			- TODO Enable Edit PO
			  :LOGBOOK:
			  CLOCK: [2026-01-07 Wed 16:07:55]
			  :END:
		- TODO Re-test Company PO Listing Page filters
		- Closing Po
			- TODO Enable Goods Received Closing
			- TODO Enable Extra Receiving Quantity
				- | Toggle | Screenshot |
				  | --- | --- |
				  | **Enabled** | ![Screenshot 2026-01-08 at 11.41.56 AM.png](../assets/Screenshot_2026-01-08_at_11.41.56 AM_1767843745201_0.png){:height 254, :width 531} |
				  | **Disabled** | ![Screenshot 2026-01-08 at 11.44.09 AM.png](../assets/Screenshot_2026-01-08_at_11.44.09 AM_1767843900502_0.png){:height 168, :width 536} |
			- TODO Enable FOC Quantities
			  collapsed:: true
				- | Toggle | Screenshot |
				  | --- | --- |
				  | **Enabled** | ![image.png](../assets/image_1767844171099_0.png) |
				  | **Disabled** | ![image.png](../assets/image_1767844255138_0.png) |
			- TODO Enable Invoice Received Closing
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
	- ### Individual PO Form Setting {{renderer :todomaster}}
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