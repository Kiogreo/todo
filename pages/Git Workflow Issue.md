# Objective
	- Understand the current pain point of our Git Workflow
	- Propose a possible long term solution & standards to solve the problem
- # Background
	- Current Workflow
		- {{renderer :mermaid_6965ef9c-82c8-4af3-af68-443c19f34221, 3}}
			- ```mermaid
			  ---
			  title: Current Git Workflow
			  ---
			  
			  gitGraph
			  	commit
			      branch staging
			      branch ST-XXXX/FEAT/feature-context
			      commit
			      commit
			      merge staging
			      commit
			      commit
			  
			  ```
- # Proposed Git Workflow