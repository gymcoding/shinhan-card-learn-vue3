<template>
	<div>
		<p>name: {{ teacher.name }}</p>
		<!-- <p>강의가 있습니까?: {{ teacher.lectures.length > 0 ? '있음' : '없음' }}</p> -->
		<p>강의가 있습니까?: {{ hasLecture }}</p>
		<p>강의가 있습니까?: {{ existLecture() }}</p>
		<h2>이름</h2>
		<p>{{ fullName }}</p>
		<button v-on:click="count++">click</button>
		{{ count }}
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup() {
		const teacher = reactive({
			name: '짐코딩',
			lectures: ['HTML/CSS', 'JavaScript', 'Vue3'],
		});

		const hasLecture = computed(() => {
			console.log('run computed');
			return teacher.lectures.length > 0 ? '있음' : '없음';
		});
		console.log('hasLecture: ', hasLecture.value);
		hasLecture.value = 'hello';
		const existLecture = () => {
			console.log('run function');
			return teacher.lectures.length > 0 ? '있음' : '없음';
		};

		const firstName = ref('홍');
		const lastName = ref('길동');

		const fullName = computed({
			get() {
				return firstName.value + ' ' + lastName.value;
			},
			set(value) {
				console.log('set value: ', value);
				[firstName.value, lastName.value] = value.split(' '); // ['짐', '코딩'];
			},
		});
		fullName.value = '짐 코딩';

		const count = ref(0);

		return {
			teacher,
			hasLecture,
			existLecture,
			fullName,
			count,
		};
	},
};
</script>

<style lang="scss" scoped></style>
