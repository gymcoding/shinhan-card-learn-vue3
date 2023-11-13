<template>
	<div>
		<div id="modifiers">
			<div @click.capture.self.once="clickDiv">
				DIV 영역
				<p @click="clickP">
					P 영역
					<span @click="clickSpan"> SPAN 영역 </span>
				</p>
			</div>
		</div>
		<a href="https://naver.com" @click.prevent>naver</a>
		<form v-on:submit.prevent="handleSubmit">
			<label for="username"></label>
			<input type="text" />
			<button type="submit">제출</button>
		</form>
	</div>
</template>

<script>
export default {
	setup() {
		const clickDiv = () => {
			console.log('clickDiv');
			// location.href = 'https://naver.com';
		};
		const clickP = () => {
			console.log('clickP');
		};
		const clickSpan = event => {
			// event.stopPropagation();
			console.log('clickSpan');
		};
		// click

		const handleSubmit = event => {
			console.log('데이터 저장~!');
		};
		return {
			clickDiv,
			clickP,
			clickSpan,
			handleSubmit,
		};
	},
};
</script>

<style scoped>
#modifiers div,
#modifiers p,
#modifiers span {
	padding: 40px;
}
#modifiers div {
	background-color: #ccc;
}
#modifiers p {
	background-color: #999;
}
#modifiers span {
	background-color: #666;
	display: block;
}
</style>
