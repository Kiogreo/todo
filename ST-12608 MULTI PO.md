## Demo {{renderer :todomaster}}
collapsed:: true
	- DONE 2025-11-20
	- DONE Feedback after DEMO
	  collapsed:: true
		- Not included
			- PO Setting not included
			- Multi draft is not included
- ##  Deployment Checklist {{renderer :todomaster}}
  collapsed:: true
	- {{renderer :todomaster}}
		- DONE pre & post deployment checklist: https://supplycart.atlassian.net/browse/ST-13221
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
		  CLOCK: [2025-12-28 Sun 20:16:11]--[2025-12-28 Sun 20:16:11] =>  00:00:00
		  CLOCK: [2025-12-28 Sun 20:16:13]--[2025-12-28 Sun 20:16:13] =>  00:00:00
		  CLOCK: [2026-01-03 Sat 11:09:19]--[2026-01-03 Sat 11:09:19] =>  00:00:00
		  CLOCK: [2026-01-03 Sat 11:09:20]--[2026-01-03 Sat 11:09:24] =>  00:00:04
		  :END:
- ## Bugs {{renderer :todomaster}}
	- ### Round 1 {{renderer :todomaster}}
	  collapsed:: true
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
			- DONE Multi PO **Submission CSV** consist Form Name column
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
			- DONE User redirected to single My PO listing page instead
		- DONE **deactivated** form type
			- DONE **Copy button** for PO that previously submitted using **deactivated** form type should be blocked with hover message
				- DONE Copy button is NOT blocked and user able to create as new draft and proceed to submit
			- DONE **Revise button** for PO that previously submitted using **deactivated** form type should be blocked with hover message
				- DONE Copy button is NOT blocked and user able to create revision draft and proceed to submit
		- DONE **deleted** form type
			- DONE **Copy button** for PO that previously submitted using **deleted** form type should be blocked with hover message
				- DONE Copy button is NOT blocked, however upon clicked, system throw error message and no copied draft created
			- DONE **Revise button** for PO that previously submitted using **deleted** form type should be blocked with hover message
				- DONE Revise button is NOT blocked and user able to create revision draft though unable to proceed until submit form
			- DONE [LUQMAN] Approving PO form which using a deleted form Setting
				- done System throws error
			- DONE [LUQMAN] Approving on behalf PO form which using a deleted form Setting
				- DONE System throws error
		- DONE Module Menu
			- DONE Single PO and Multi PO modules should not exist simultaneously
				- DONE Both Single and Multi PO modules appear together
			- DONE Multi PO sub‑option in sidebar consist GR Listing page
				- DONE Missing sub‑option for GR Listing page
			- DONE Multi PO sub‑option in sidebar consist RTN Listing page
				- DONEMissing sub‑option for RTN Listing page
			- DONE Multi PO sub‑option in sidebar consist PI Listing page
				- DONE Missing sub‑option for PI Listing page
	- ### Round 2 {{renderer :todomaster}}
	  collapsed:: true
		- DONE ## New bugs 1
		  collapsed:: true
		  :LOGBOOK:
		  CLOCK: [2025-12-28 Sun 20:15:48]--[2025-12-28 Sun 20:15:49] =>  00:00:01
		  CLOCK: [2026-01-02 Fri 22:14:12]--[2026-01-02 Fri 22:14:14] =>  00:00:02
		  CLOCK: [2026-01-02 Fri 22:14:14]--[2026-01-02 Fri 22:14:15] =>  00:00:01
		  CLOCK: [2026-01-05 Mon 08:08:32]--[2026-01-05 Mon 08:08:32] =>  00:00:00
		  CLOCK: [2026-01-05 Mon 08:08:42]--[2026-01-05 Mon 08:08:50] =>  00:00:08
		  :END:
			- DONE Search filter function in My PO listing page is not working
			- DONE Expected result
				- DONE User able to search based on search option availability
		- DONE ## **New bugs 2**
		  collapsed:: true
			- DONE **Copy button** for PO always showing hover message of “Copying disabled as the form used has been deleted/deactivated“ even though the form still exist and active
		- DONE ## **New bugs 3**
		  collapsed:: true
			- DONE **Revise button** for PO always showing hover message of “Copying disabled as the form used has been deleted/deactivated“ even though the form still exist and active
		- DONE ## New bugs 4
		  collapsed:: true
			- DONE Users are not auto assigned to Default PO form
			- DONE **Solution**
				- DONE create new migration file utk assign default form setting to existing user
				  :LOGBOOK:
				  CLOCK: [2026-01-05 Mon 08:21:04]--[2026-01-05 Mon 08:21:05] =>  00:00:01
				  :END:
		- DONE ## New bugs 5
		  collapsed:: true
		  :LOGBOOK:
		  CLOCK: [2026-01-05 Mon 08:08:48]--[2026-01-05 Mon 08:08:49] =>  00:00:01
		  CLOCK: [2026-01-05 Mon 08:09:09]--[2026-01-05 Mon 08:09:09] =>  00:00:00
		  CLOCK: [2026-01-05 Mon 08:10:04]--[2026-01-05 Mon 08:10:05] =>  00:00:01
		  CLOCK: [2026-01-05 Mon 08:10:06]--[2026-01-05 Mon 08:10:08] =>  00:00:02
		  :END:
			- DONE `QTM/PO/00266` is not showing in both My and Company PO listing page
		- DONE ## New bugs 6
		  collapsed:: true
			- DONE Migration on form setting **mapping for RFX → PR**. Currently, RFX form also being auto assigned to PO default form even when using configuration = RQ > RFX > PR > PO
			- DONE **Solution**
				- DONE remove mapping to PO for any company that uses RFX configuration of `RQ > RFX > PR > PO` when running the `php artisan multi-po:set-default-po-form-setting-and-mapping`
		- DONE ## New bugs 7
		  collapsed:: true
			- DONE User manual invite should have PO form assignation as per all other modules
			  :LOGBOOK:
			  CLOCK: [2026-01-05 Mon 08:21:15]--[2026-01-05 Mon 08:21:16] =>  00:00:01
			  :END:
			- DONE **Solution**
				- DONE Add PO form assignation in user manual invite (go to: `Settings` > `Users` > Click on the plus icon `+`)
		- DONE ## New bugs 8
		  collapsed:: true
		  :LOGBOOK:
		  CLOCK: [2026-01-05 Mon 08:09:08]--[2026-01-05 Mon 08:09:10] =>  00:00:02
		  CLOCK: [2026-01-05 Mon 08:09:10]--[2026-01-05 Mon 08:09:11] =>  00:00:01
		  CLOCK: [2026-01-05 Mon 08:09:11]--[2026-01-05 Mon 08:09:12] =>  00:00:01
		  CLOCK: [2026-01-05 Mon 08:09:12]--[2026-01-05 Mon 08:09:14] =>  00:00:02
		  :END:
			- DONE User bulk invite should have PO form assignation as per all other modules
			- DONE **Solution**
				- DONE Add PO form assignation in user bulk invite's CSV document
		- DONE Able to perform **PO form assignment via user profile**
		  collapsed:: true
		  :LOGBOOK:
		  CLOCK: [2026-01-05 Mon 08:10:11]--[2026-01-05 Mon 08:10:11] =>  00:00:00
		  :END:
			- DONE Able to perform **PO form assignment via user profile**
				- DONE User still able to access any unassigned PO form in form draft (at form selection stage)
			- DONE **Solution**
				- DONE add checking in the PO draft form step 1 (form selection screen) to not allow unassigned user
				- DONE Or it could be due to chaching
		- DONE Able to perform **user assignment via PO form setting**
		  collapsed:: true
			- DONE User still able to access any unassigned PO form in form draft (at form selection stage)
			- DONE **Solution**
				- DONE add checking in the PO draft form step 1 (form selection screen) to not allow unassigned user
				- DONE Or it could be due to chaching
	- ### Post LIVE {{renderer :todomaster}}
		- DONE [#A] [[Single PO filter button missing]] https://supplycart.atlassian.net/browse/ST-13270
		  :LOGBOOK:
		  CLOCK: [2026-01-05 Mon 08:08:45]--[2026-01-05 Mon 08:08:54] =>  00:00:09
		  :END:
		- DONE [#B] https://supplycart.atlassian.net/browse/ST-13271
		  collapsed:: true
			- PR
				- https://github.com/supplycart/adam/pull/8037
			- Root cause
				- missed out feature
		- DOING [#B] https://supplycart.atlassian.net/browse/ST-13272
		  collapsed:: true
		  :LOGBOOK:
		  CLOCK: [2026-01-05 Mon 09:59:02]--[2026-01-05 Mon 14:33:26] =>  04:34:24
		  CLOCK: [2026-01-05 Mon 14:33:26]
		  :END:
			- PR
			- Root cause
-