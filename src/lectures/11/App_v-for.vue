<template>
	<div>
		<ul>
			<!-- v-for 반복문 디렉티브 -->
			<li v-for="(item, index) in evenItems" v-bind:key="item.id">
				<!-- <template v-if="item.id % 2 === 0"> -->
				index: {{ index }}, {{ item.id }}, {{ item.message }}
				<!-- </template> -->
			</li>
		</ul>
		<ul>
			<li v-for="(value, key, index) in myObject" :key="key">
				index: {{ index }}, key: {{ key }}, value: {{ value }}
			</li>
		</ul>
	</div>
</template>

<script>
import { computed, reactive } from 'vue';

export default {
	setup() {
		const items = reactive([
			{ id: 1, message: 'Java' },
			{ id: 2, message: 'HTML' },
			{ id: 3, message: 'CSS' },
			{ id: 4, message: 'JavaScript' },
		]);

		const myObject = reactive({
			title: '제목',
			author: '홍길동',
			publishedAt: '2016-01-01',
		});

		const evenItems = computed(() => items.filter(item => item.id % 2 === 0));

		return { items, evenItems, myObject };
	},
};
</script>

<style lang="scss" scoped></style>
