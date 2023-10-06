<template>
	<div class="ui vertical segment">
		<div class="flexbox">
			<div class="flex-content">
				<h3>Number type Option Value ModelList</h3>
				<div class="button-group">
					<button type="button" @click="reset3" class="small ui button">reset</button>
					<button type="button" @click="selectOption3" class="small ui button">option select from parent</button>
				</div>
				<div>
					<model-list-select
														 :list="options3"
														 v-model="numberItem"
														 option-value="id"
														 :custom-text="idAndNameAndDesc"
														 placeholder="select item2">
					</model-list-select>
				</div>
			</div>
			<div class="flex-result">
				<table class="ui celled table">
					<thead>
						<tr>
							<th>value(number)</th>
						</tr>
					</thead>
					<tbody>
						<tr>
							<td>{{ numberItem }}</td>
						</tr>
					</tbody>
				</table>
			</div>
		</div>
	</div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { ModelListSelect } from "vue-search-select";

interface Item {
	id: string;
	name: string;
	desc: string;
}

const options3 = [
	{ id: 0, name: "a0", desc: "desc00" },
	{ id: 1, name: "aa", desc: "desc01" },
	{ id: 2, name: "ab", desc: "desc02" },
	{ id: 3, name: "bc", desc: "desc03" },
	{ id: 4, name: "cd", desc: "desc04" },
	{ id: 5, name: "de", desc: "desc05" },
	{ id: 6, name: "ef", desc: "desc06" },
];
const numberItem = ref<number | null>(null);

function idAndNameAndDesc(item: Item) {
	return `${item.id} - ${item.name} - ${item.desc}`;
}
function reset3() {
	numberItem.value = null;
}
function selectOption3() {
	// select option from parent component
	numberItem.value = options3[0].id;
}

</script>
