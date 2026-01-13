# Objective
	- Understand the current pain point of our Git Workflow
	- Propose a possible long term solution & standards to solve the problem
- # Background
	- {{renderer :mermaid_6965eed2-a046-4f1e-b2d9-15381c1d19da, 3}}
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