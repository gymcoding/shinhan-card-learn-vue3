<template>
	<div>
		<h2>input value</h2>
		<input type="text" v-model.lazy="inputValue" />
		<!-- <input type="text" v-model="inputValue" /> -->
		<!-- <input
			type="text"
			:value="inputValue"
			@input="event => (inputValue = event.target.value)"
		/> -->
		<p>{{ inputValue }}</p>

		<h2>textarea value</h2>
		<textarea v-model="textareValue"></textarea>

		<h2>checkbox value</h2>
		<label>
			HTML
			<input type="checkbox" value="html" v-model="checkboxValues" />
		</label>
		<label>
			CSS
			<input type="checkbox" value="css" v-model="checkboxValues" />
		</label>
		<label>
			JavaScript
			<input type="checkbox" value="javascript" v-model="checkboxValues" />
		</label>
		{{ checkboxValues }}
		<hr />

		<select v-model="selectValue">
			<option value="html">HTML 수업</option>
			<option value="css">CSS 수업</option>
			<option value="javascript">JS 수업</option>
		</select>
		{{ selectValue }}
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const inputValue = ref('hello');
		const textareValue = ref('');
		const checkboxValue = ref('');
		const checkboxValues = ref([]);
		const radioValue = ref('');
		const selectValue = ref('');

		return {
			inputValue,
			textareValue,
			checkboxValue,
			checkboxValues,
			radioValue,
			selectValue,
		};
	},
};
</script>

<style lang="scss" scoped></style>
