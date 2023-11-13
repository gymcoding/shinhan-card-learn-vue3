<template>
	<div>
		<input type="text" @keypress.ctrl.enter="addTodo" />
		<ul>
			<li v-for="todo in todos" :key="todo">
				{{ todo }}
			</li>
		</ul>
	</div>
</template>

<script>
import { reactive } from 'vue';

export default {
	setup() {
		const todos = reactive(['vue 학습하기']);
		const addTodo = event => {
			console.log('addTodo');
			todos.push(event.target.value);
			event.target.value = '';
			event.target.focus();
		};
		return {
			todos,
			addTodo,
		};
	},
};
</script>

<style lang="scss" scoped></style>
