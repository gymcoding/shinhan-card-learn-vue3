<template>
	<div>
		<div v-memo="[subscribers, views]">
			<p>subscribers: {{ subscribers }}</p>
			<p>views: {{ views }}</p>
			<p>likes: {{ likes }}</p>
		</div>
		<div>
			<p>subscribers: {{ subscribers }}</p>
			<p>views: {{ views }}</p>
			<p>likes: {{ likes }}</p>
		</div>
		<button v-on:click="subscribers++">Subs++</button>
		<button v-on:click="views++">Views++</button>
		<button v-on:click="likes++">Likes++</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const subscribers = ref(4000);
		const views = ref(400);
		const likes = ref(20);
		return {
			subscribers,
			views,
			likes,
		};
	},
};
</script>

<style lang="scss" scoped></style>
