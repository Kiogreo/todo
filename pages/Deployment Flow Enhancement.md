## Meetings {{renderer :todomaster}}
	- DOING Meeting with Sim + DevOps + Tech + QA
	  :LOGBOOK:
	  CLOCK: [2026-02-26 Thu 14:45:55]
	  :END:
	- TODO Meeting with Management (DevOps + Sim + Shangrong + Ben + Jasper)
- ## Notes
	- ### Proposal
		- | **AGREED?** | **FLOW #** | **BATCH** | **SERVER** | **REMARKS** |
		  | --- | --- | --- | --- |
		  | ✅️ | 1 | 1 batch | `1` server | When some ticket fails QA, the whole batch will be discarded and a new batch will be created consisting only the ticket that passes QA to be deployed to `Alpha` environment |
		  | | 2 | ❌️ | `1` server | |
		  | | 3 | 1 batch | `1` server | When some ticket fails QA, only the passed QA tickets will be deployed to `Beta` environment |
		  | | 4 | ❌️ | `M` server | |
	- ## Diagram
		- ### Happy Flow
			- {{renderer :mermaid_699ff3db-fd53-440a-8d3f-527ca29ca87d, 3}}
			  collapsed:: true
				- ```mermaid
				  block
				      block:Ticket
				          T1
				          T2
				          T3
				      end
				      space
				      Alpha
				      Ticket --> Alpha
				      space
				      Alpha --> Beta
				      space
				      Beta --> PROD
				  ```
		- ### Alternative Flow
			- {{renderer :mermaid_699ff3db-fd53-440a-8d3f-527ca29ca87d, 3}}
			  collapsed:: true
				- ```mermaid
				  block
				      block:Ticket
				          T1["TI ✅️"]
				          T2["T2 (❌️ fail)"]
				          T3["T3 ✅️"]
				      end
				      space
				      Alpha["Alpha (❌️ discarded)"]
				      Ticket --> Alpha
				  ```
			- {{renderer :mermaid_699ff807-1448-42a9-b56b-81bddde179e4, 3}}
			  collapsed:: true
				- ```mermaid
				  block
				      block:Ticket
				          T1["TI ✅️"]
				          T3["T3 ✅️"]
				      end
				      space
				      Alpha["Alpha (new)"]
				      Ticket --> Alpha
				      space
				      Alpha --> Beta
				      space
				      Beta --> PROD
				  ```
	- ### Management Consideration
		- Current VS New Flow
			- | **TOPIC** | **CURRENT FLOW** | **NEW FLOW** |
			  | --- | --- | --- |
			  | Deployment Frequency | Every 2 weeks | Multiple per week, every week or/and every 2 week (a lot more flexible) |
			  | Deployment Ticket Quantity | Between 5-20+ ticket per deployment | Expecting less than current flow |
			  | Deployment Environment | Current Staging is 24/7 up-time | New Alpha & Beta Environment will be on demand (scalable) |
			  | Cherry-Pick Deployment | ✅️ | ❌️ |
		- Deployment Expectation
			- Frequency
				- We have the flexibility to either proceed with the current deployment schedule or change it to depending on the deployment batch and situations
			- Ticket Quantity
				- We can expect to reduce the number of tickets to deploy per deployment window from 10+ tickets to less than 7
		- On demand Beta environment
			-
		- No more cherry-pick deployment
			- Since both Alpha & Beta environment is on demand, there will