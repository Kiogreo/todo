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
		      commit id: "Normal" tag: "v1.0.0"
		            commit
		            commit id: "Reverse" type: REVERSE tag: "RC_1"
		            commit
		            commit id: "Highlight" type: HIGHLIGHT tag: "8.8.4"
		            commit
		  ```
- # Proposed Git Workflow