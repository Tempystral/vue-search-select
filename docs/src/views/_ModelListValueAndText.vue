<template>
	<div class="ui vertical segment">
		<div class="flexbox">
			<div class="flex-content">
				<h3>OptionValue & OptionText prop</h3>
				<div class="button-group">
					<button type="button" @click="reset" class="small ui button">reset</button>
					<button type="button" @click="selectOption" class="small ui button">option select from parent</button>
				</div>
				<div>
					<model-list-select
														 :list="options"
														 v-model="objectItem"
														 option-value="code"
														 option-text="name"
														 id="mySelectId"
														 name="mySelectName"
														 placeholder="select item"
														 @searchchange="printSearchText"
														 @blur="handleBlur">
					</model-list-select>
				</div>
			</div>
			<div class="flex-result">
				<h4>input text(searchText)</h4>
				<p>{{ searchText }}</p>
				<table class="ui celled table">
					<thead>
						<tr>
							<th>code</th>
							<th>name</th>
							<th>desc</th>
						</tr>
					</thead>
					<tbody>
						<tr>
							<td>{{ objectItem.code }}</td>
							<td>{{ objectItem.name }}</td>
							<td>{{ objectItem.desc }}</td>
						</tr>
					</tbody>
				</table>
			</div>
		</div>
	</div>
</template>

<script setup lang="ts">
import { ModelListSelect } from "vue-search-select"
import { ref } from 'vue';

const options = [
	{ code: "01", name: "aa", desc: "desc01" },
	{ code: "02", name: "ab", desc: "desc02" },
	{ code: "03", name: "bc", desc: "desc03" },
	{ code: "04", name: "cd", desc: "desc04" },
	{ code: "05", name: "de", desc: "desc05" },
	{ code: "06", name: "ef", desc: "desc06" },
];

const objectItem = ref({
	code: "",
	name: "",
	desc: "",
});

const searchText = ref("");

function reset() {
	objectItem.value = {
		code: "",
		name: "",
		desc: "",
	};
}
function selectOption() {
	// select option from parent component
	objectItem.value = options[0];
}

function printSearchText(text: string) {
	searchText.value = text;
}

function handleBlur() {
	console.log("handleBlur");
}
</script>
