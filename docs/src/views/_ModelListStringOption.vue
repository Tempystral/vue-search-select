<template>
	<div class="ui vertical segment">
		<div class="flexbox">
			<div class="flex-content">
				<h3>String type Option value ModelList</h3>
				<div class="button-group">
					<button type="button" @click="reset2" class="small ui button">reset</button>
					<button type="button" @click="selectOption2" class="small ui button">option select from parent</button>
				</div>
				<div>
					<model-list-select
														 :list="options2"
														 v-model="stringItem"
														 option-value="code"
														 :custom-text="codeAndNameAndDesc"
														 placeholder="select item2">
					</model-list-select>
				</div>
			</div>
			<div class="flex-result">
				<table class="ui celled table">
					<thead>
						<tr>
							<th>value(string)</th>
						</tr>
					</thead>
					<tbody>
						<tr>
							<td>{{ stringItem }}</td>
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
	code: string;
	name: string;
	desc: string;
}

const options2 = [
	{ code: "str01", name: "aa", desc: "desc01" },
	{ code: "str02", name: "ab", desc: "desc02" },
	{ code: "str03", name: "bc", desc: "desc03" },
	{ code: "str04", name: "cd", desc: "desc04" },
	{ code: "str05", name: "de", desc: "desc05" },
	{ code: "str06", name: "ef", desc: "desc06" },
];
const stringItem = ref("");

function codeAndNameAndDesc(item: Item) {
	return `${item.code} - ${item.name} - ${item.desc}`;
}

/* sample 2 */
function reset2() {
	stringItem.value = "";
}
function selectOption2() {
	// select option from parent component
	stringItem.value = options2[0].code;
}
</script>
