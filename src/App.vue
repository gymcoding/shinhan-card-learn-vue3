<template>
	<div>
		<TheNav />

		<TheView />
	</div>
</template>

<script>
import { provide, ref } from 'vue';
import TheNav from './components/TheNav.vue';
import TheView from './components/TheView.vue';
export default {
	components: {
		TheNav,
		TheView,
	},
	setup() {
		const appMessage = ref('hello vue3 application!');
		provide('appMessage', appMessage);
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
