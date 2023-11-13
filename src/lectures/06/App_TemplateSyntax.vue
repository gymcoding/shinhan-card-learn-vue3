<template>
	<div>
		<h2>보간법</h2>
		<p>{{ message }}</p>
		<p v-once>{{ message }}</p>
		<button v-on:click="message = message + '!'">add message</button>
		<h2>HTML</h2>
		<p v-html="rawHtml"></p>
		<h2>Reverse message</h2>
		{{ message.split('').reverse().join('') }}
		{{ visible ? '예' : '아니오' }}
		<h2>v-bind</h2>
		<!-- <input v-bind:type="inputType" v-bind:placeholder="placeholder" />
		<input :type="inputType" :placeholder="placeholder" /> -->
		<input v-bind="attrs" />
		<br />
		<br />
		<br />
		<br />
		<br />
		<br />
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const message = ref('Hello Vue3');

		const rawHtml = ref('<strong>html</strong>');

		const visible = ref(true);

		const placeholder = ref('값을 입력해주세요!');
		const inputType = ref('password');
		const attrs = ref({
			type: 'text',
			placeholder: '비밀번호를 입력해주세요!',
			value: '짐코딩',
		});
		return {
			message,
			rawHtml,
			visible,
			placeholder,
			inputType,
			attrs,
		};
	},
};
</script>

<style lang="scss" scoped></style>
