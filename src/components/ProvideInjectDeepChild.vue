<template>
	<div class="card">
		<div class="card-header">Deep Child Component</div>
		<div class="card-body">
			<p>{{ appMesssage }}</p>
			<p>{{ counter }}</p>
		</div>
	</div>
</template>

<script>
import { inject } from 'vue';

export default {
	setup() {
		const appMesssage = inject('appMessage');
		const counter = inject('counter');
		const incrementCount = inject('incrementCount');
		incrementCount();
		incrementCount();
		incrementCount();
		incrementCount();
		return {
			appMesssage,
			counter,
		};
	},
};
</script>

<style lang="scss" scoped></style>
