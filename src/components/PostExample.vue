<template>
	<main>
		<div class="container py-4">
			<FancyButton> <span>Fancy Button</span> </FancyButton>
			<AppCard>
				<template #header="{ headerMessage }"> {{ headerMessage }} </template>
				<template #default="props">
					<FancyButton>
						<div>{{ props.childMessage }}</div>
						<div>{{ props.hello }}</div>
						<div>{{ props.say }}</div>
					</FancyButton>
				</template>
				<template #footer> 푸터입니다. </template>
			</AppCard>

			<div class="row g-3">
				<PostCreate @create-post="createPost" />
				<template v-for="post in posts" :key="post.id">
					<div class="col col-4">
						<PostItem
							:title="post.title"
							:contents="post.contents"
							:is-like="post.isLike"
							:type="post.type"
							@toggle-like="toggleLike(post)"
						/>
					</div>
				</template>
			</div>

			<!-- :firstname="firstname"
			@update:firstname="value => (firstname = value)" -->
			<Username v-model:firstname="firstname" v-model:lastname="lastname" />
			<LabelInput
				class="parent-class"
				id="parent-id"
				style="background: red"
				data-id="hello"
				label="우리가 정의한 것!!!"
				label2="우리가 정의하지 않ㅇ느것!!!"
				@click2="toggleLike"
			/>
		</div>
	</main>
</template>

<script>
import PostItem from '@/components/PostItem.vue';
import AppCard from './AppCard.vue';
import { reactive, ref } from 'vue';
import PostCreate from './PostCreate.vue';
import LabelInput from './LabelInput.vue';
import Username from './Username.vue';
import FancyButton from './FancyButton.vue';
export default {
	components: {
		PostItem,
		PostCreate,
		Username,
		LabelInput,
		FancyButton,
		AppCard,
	},
	setup() {
		const post = ref({
			title: '제목입니다!!',
			contents: '내용',
		});

		const posts = reactive([
			{
				id: 1,
				title: '제목1',
				contents: '내용1',
				isLike: true,
				type: 'news',
				obj: { status: false },
			},
			{
				id: 2,
				title: '제목2',
				contents: '내용2',
				isLike: true,
				type: 'news',
				obj: { status: false },
			},
			{
				id: 3,
				title: '제목3',
				contents: '내용3',
				isLike: true,
				type: 'news',
				obj: { status: false },
			},
			{
				id: 4,
				title: '제목4',
				contents: '내용4',
				isLike: false,
				type: 'notice',
				obj: { status: false },
			},
			{
				id: 5,
				title: '제목5',
				contents: '내용5',
				isLike: false,
				type: 'notice',
				obj: { status: false },
			},
			{
				id: 6,
				title: '제목6',
				contents: '내용6',
				isLike: false,
				type: 'notice',
				obj: { status: false },
			},
		]);
		const toggleLike = post => {
			console.log('toggleLike');
			post.isLike = !post.isLike;
		};

		const createPost = newPost => {
			console.log('createPost: ', newPost);
			posts.push(newPost);
		};

		const username = ref('홍길동');
		const firstname = ref('홍');
		const lastname = ref('길동');
		return {
			post,
			posts,
			toggleLike,
			createPost,
			username,
			firstname,
			lastname,
		};
	},
};
</script>

<style lang="scss" scoped></style>
