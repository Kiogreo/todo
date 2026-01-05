- Both FE & BE
	- any existing supplycart libraries that are implemented within Adama/Hub/Eva
	- https://github.com/supplycart/money
	- https://github.com/supplycart/ui
- FE standard
	- Helper libraries
	- Some codes/components to avoid
		- `hasPermission()` (resources/js/constants/permissions/index.js)
		- resources/js/mixins/auth.js
			- Create multi composable for mixins
		- resources/js/components/shared/buttons/DownloadBulkCreateAddButton.vue
	- Global variable
		- company setting
		- user setting
	- IDE extenstion
		- vscode
			- VUE
				- https://marketplace.visualstudio.com/items?itemName=mubaidr.vuejs-extension-pack
				- https://marketplace.visualstudio.com/items?itemName=sdras.vue-vscode-snippets
				- https://marketplace.visualstudio.com/items?itemName=Vue.volar
			- InertiaJs
				- https://marketplace.visualstudio.com/items?itemName=nhedger.inertia
					- replace: https://marketplace.visualstudio.com/items?itemName=Vue.volar
- Vue3
	- DONE FE code must compatible Vue3
		- DONE Show example how to verify
	- Vue Single Component
		- properties/function position guideline (based on our eslint)
	- New Component
		- Lazy loading component use `defineAsyncComponent()` (always use this for Vue3 compatibility)
			- import { computed, defineAsyncComponent } from "vue";
		- Nested `<template>` directive
			- ```vue
			  <template #button>
			  	<div class="btn btn-default m-0-i">
			        {{ trans.get("shared.action_labels.filter") }}
			    </div>
			  </template>
			  
			  <template>
			  	<div class="dropdown-filter grid space-y-2 p-3 pb-2"
			           <div class="grid grid-cols-3">
			  	<label class="col-span-1 mb-0" for="status">
			    Status`
			  ```
		- Supplycart/ui repo
			- re-useable component that we can use cross-project
			- utamakan yg drp supplycart/ui