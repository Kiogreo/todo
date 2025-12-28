## Demo
collapsed:: true
	- DONE 2025-11-20
	- TODO Feedback after DEMO
		- [ ] Not included
			- [ ] PO Setting not included
			- [ ] Multi draft is not included
- ##  Deployment Checklist
	- {{renderer :todomaster}}
		- TODO pre & post deployment checklist: https://supplycart.atlassian.net/browse/ST-13221
		  :LOGBOOK:
		  CLOCK: [2025-12-28 Sun 17:00:04]--[2025-12-28 Sun 17:01:42] =>  00:01:38
		  CLOCK: [2025-12-28 Sun 17:01:43]--[2025-12-28 Sun 17:01:48] =>  00:00:05
		  CLOCK: [2025-12-28 Sun 17:01:49]--[2025-12-28 Sun 17:01:51] =>  00:00:02
		  CLOCK: [2025-12-28 Sun 17:01:54]--[2025-12-28 Sun 17:01:55] =>  00:00:01
		  CLOCK: [2025-12-28 Sun 17:01:57]--[2025-12-28 Sun 17:01:58] =>  00:00:01
		  CLOCK: [2025-12-28 Sun 17:01:58]--[2025-12-28 Sun 17:01:58] =>  00:00:00
		  CLOCK: [2025-12-28 Sun 17:01:59]--[2025-12-28 Sun 17:02:00] =>  00:00:01
		  CLOCK: [2025-12-28 Sun 17:02:02]--[2025-12-28 Sun 17:02:02] =>  00:00:00
		  CLOCK: [2025-12-28 Sun 17:02:02]--[2025-12-28 Sun 17:02:03] =>  00:00:01
		  :END:
- ## Bugs
	- {{renderer :todomaster}}
		- DONE Assignment
			- DONE Migration on form setting **mapping for RFX → PO** default form
				- DONE Migration was not done
			- DONE **PO form assignment via user profile**
				- DONE PO form assignments in user profile does not exist
			- DONE Able to perform **user assignment via PO form setting**
				- DONE User assignment tab in PO form setting does not exist
		- DONE Email
			- DONE **Submission email** consist PO form name
				- DONE Email was triggered without PO form name
			- DONE **Approval email** consist PO form name
				- DONE Email was triggered without PO form name
		- DONE **Form Details page** consist form name
			- DONE Form name is not showing in form details page
		- DONE Listing Pages
			- DONE Multi PO **My Listing page** consist Form Name column
				- DONE Form Name column missing
			- DONE Multi PO **Company Listing page** consist Form Name column
				- DONE Form Name column missing
			- DONE Multi PO **Company Listing page** consist filter option by Form Name
				- DONE No option to filter by form name
- DONE CSV
	- DONEMulti PO **Submission CSV** consist Form Name column
		- DONE CSV headers missing Form Name field
	- DONE Multi PO **Item CSV** consist Form Name column
		- DONE CSV headers missing Form Name field
- DONE [LUQMAN] **Budget Details page** showing all different Form Type name for PO module
	- DONE PO form type name populated in Budget Details page using default name only, not based on the latest form name
- DONE [ZIKRI] User able to click “previous“ button in multi PO draft to redirect back to the form selection level page
	- DONE User stays in submission level page
- DONE [ZIKRI] Deleted PO form type should not be visible during form selection stage in PO draft
	- DONE Deleted form type still appears in selection list
- DONE [ZIKRI] Cancelling multi PO draft should redirect user back to Multi PO listing page
	- DOINE User redirected to single My PO listing page instead
- DONE **deactivated** form type
	- DONE **Copy button** for PO that previously submitted using **deactivated** form type should be blocked with hover message
		- DONE Copy button is NOT blocked and user able to create as new draft and proceed to submit
	- DONE **Revise button** for PO that previously submitted using **deactivated** form type should be blocked with hover message
		- DONE Copy button is NOT blocked and user able to create revision draft and proceed to submit
- DONE **deleted** form type
	- DONE **Copy button** for PO that previously submitted using **deleted** form type should be blocked with hover message
		- DONE Copy button is NOT blocked, however upon clicked, system throw error message and no copied draft created
	- [x] **Revise button** for PO that previously submitted using **deleted** form type should be blocked with hover message
		- [x] Revise button is NOT blocked and user able to create revision draft though unable to proceed until submit form
	- [x] [LUQMAN] Approving PO form which using a deleted form Setting
		- [x] System throws error
	- [x] [LUQMAN] Approving on behalf PO form which using a deleted form Setting
		- [x] System throws error
- [x] Module Menu
	- [x] Single PO and Multi PO modules should not exist simultaneously
		- [x] Both Single and Multi PO modules appear together
	- [x] Multi PO sub‑option in sidebar consist GR Listing page
		- [x] Missing sub‑option for GR Listing page
	- [x] Multi PO sub‑option in sidebar consist RTN Listing page
		- [x] Missing sub‑option for RTN Listing page
	- [x] Multi PO sub‑option in sidebar consist PI Listing page
		- [x] Missing sub‑option for PI Listing page
- ## New bugs (Round 2)
- [ ] ## New bugs 1
	- [ ] Search filter function in My PO listing page is not working
	- [ ] Expected result
		- [ ] User able to search based on search option availability
	- [ ] **Solution**
		- [ ]
- [x] ## **New bugs 2**
	- [x] **Copy button** for PO always showing hover message of “Copying disabled as the form used has been deleted/deactivated“ even though the form still exist and active
- [x] ## **New bugs 3**
	- [x] **Revise button** for PO always showing hover message of “Copying disabled as the form used has been deleted/deactivated“ even though the form still exist and active
- [ ] ## New bugs 4
	- [ ] Users are not auto assigned to Default PO form
	- [ ] **Solution**
		- [ ] create new migration file utk assign default form setting to existing user
- [ ] ## New bugs 5
	- [ ] `QTM/PO/00266` is not showing in both My and Company PO listing page
	- [ ] **Solution**
		- [ ]
- [ ] ## New bugs 6
	- [ ] Migration on form setting **mapping for RFX → PR**. Currently, RFX form also being auto assigned to PO default form even when using configuration = RQ > RFX > PR > PO
	- [ ] **Solution**
		- [ ] remove mapping to PO for any company that uses RFX configuration of `RQ > RFX > PR > PO` when running the `php artisan multi-po:set-default-po-form-setting-and-mapping`
- [ ] ## New bugs 7
	- [ ] User manual invite should have PO form assignation as per all other modules
	- [ ] **Solution**
		- [ ] Add PO form assignation in user manual invite (go to: `Settings` > `Users` > Click on the plus icon `+`)
- [ ] ## New bugs 8
	- [ ] User bulk invite should have PO form assignation as per all other modules
	- [ ] **Solution**
		- [ ] Add PO form assignation in user bulk invite's CSV document
- [ ] Able to perform **PO form assignment via user profile**
	- [ ] Able to perform **PO form assignment via user profile**
		- [ ] User still able to access any unassigned PO form in form draft (at form selection stage)
	- [ ] **Solution**
		- [ ] add checking in the PO draft form step 1 (form selection screen) to not allow unassigned user
		- [ ] Or it could be due to chaching
- [ ] Able to perform **user assignment via PO form setting**
	- [ ] Able to perform **user assignment via PO form setting**
		- [ ] User still able to access any unassigned PO form in form draft (at form selection stage)
	- [ ] **Solution**
		- [ ] add checking in the PO draft form step 1 (form selection screen) to not allow unassigned user
		- [ ] Or it could be due to chaching