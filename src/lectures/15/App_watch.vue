<template>
	<div>
		<label>
			검색어
			<input type="text" v-model.lazy="searchText" />
		</label>
	</div>
</template>

<script>
import { ref, watch } from 'vue';

export default {
	setup() {
		const searchText = ref('밀키트');

		watch(searchText, (newValue, oldValue) => {
			console.log('newValue: ', newValue);
			console.log('oldValue: ', oldValue);
			// 연관검색어~
			// ~
		});
		return {
			searchText,
		};
	},
};
</script>

<style lang="scss" scoped></style>
