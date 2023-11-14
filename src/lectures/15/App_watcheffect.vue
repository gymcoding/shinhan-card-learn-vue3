<template>
	<div>
		<form>
			<div>
				<input v-model.lazy="title" type="text" placeholder="제목" />
			</div>
			<div>
				<textarea
					v-model="contents"
					cols="20"
					rows="4"
					placeholder="내용"
				></textarea>
			</div>
		</form>
	</div>
</template>

<script>
import { ref, watch, watchEffect } from 'vue';

export default {
	setup() {
		const title = ref('');
		const contents = ref('');

		const save = (title, contents) => {
			console.log(`저장되었습니다. ${title} ${contents}`);
		};

		watchEffect(() => {
			console.log('watchEffect');
			save(title.value, contents.value);
		});
		watch(
			[title, contents],
			() => {
				console.log('watch');
				save(title.value, contents.value);
			},
			{
				immediate: true,
			},
		);

		return {
			title,
			contents,
		};
	},
};
</script>

<style lang="scss" scoped></style>
