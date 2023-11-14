<template>
	<div>
		<p>x: {{ x }}</p>
		<p>y: {{ y }}</p>
	</div>
</template>
<script>
import { ref, watch } from 'vue';

export default {
	setup() {
		const x = ref(0);
		const y = ref(0);

		watch([x, y], () => {
			console.log(' 변화감지 ');
		});
		return {
			x,
			y,
		};
	},
};
</script>

<style lang="scss" scoped></style>
