<template>
	<div class="card">
		<div class="card-body">
			<span class="badge bg-secondary">
				{{ tagName }}
			</span>

			<h5 class="card-title red">{{ title }}</h5>
			<p class="card-text">{{ contents }}</p>
			<a href="#" class="btn" :class="isLikeClass" @click="toggleLike">
				좋아요
			</a>
		</div>
	</div>
</template>

<script>
import { computed, ref } from 'vue';
export default {
	// props: ['title', 'contents'],
	props: {
		type: {
			type: String,
			default: 'notice',
			required: true,
			validator: value => {
				return ['news', 'notice'].includes(value);
			},
		},
		title: {
			type: [String, Number],
			required: true,
		},
		contents: {
			type: String,
			required: true,
		},
		isLike: {
			type: Boolean,
			default: true,
		},
		obj: {
			type: Object,
			default: () => ({}),
		},
	},
	setup(props, context) {
		const color = ref('red');

		const tagName = computed(() =>
			props.type === 'news' ? '뉴스' : '공지사항',
		);

		const isLikeClass = computed(function () {
			return props.isLike ? 'btn-danger' : 'btn-outline-danger';
		});

		const toggleLike = () => {
			// props.isLike = !props.isLike
			// props.obj.isLike = !props.obj.isLike;
			context.emit('toggleLike');
		};

		return { color, tagName, isLikeClass, toggleLike };
	},
};
</script>

<style scoped>
.red {
	color: v-bind(color);
}
</style>
