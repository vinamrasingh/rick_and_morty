<template>
	<section>
		<div>
			<ul
				v-for="(filter,key) in filterList"
				:key="filter.category"
				class="list-unstyled d-flex flex-column"
			>
				<h4>{{key | toUpperCase}}</h4>
				<div class="pl-3 pr-5 py-3 pl-md-2 border border-primary rounded">
					<li v-for="(filterItem, filterKey) in filter" :key="filterKey" class="form-check">
						<label for="'filter_'+filterItem.value" class="form-check-label">
							<input
								type="checkbox"
								:id="'filter_'+filterItem.value"
								v-model="filterItem.selected"
								@change="updateSelectedFilter"
								class="form-check-input"
							/>
							{{filterItem.value}}
						</label>
					</li>
				</div>
			</ul>
		</div>
	</section>
</template>
<script src="./app-filter.js">
</script>
