<template>
	<div>
		<div>Câu hỏi : {{question.content}}</div>
		<div>
			<div v-for="(answer, index) in question.answers" :key="index" @click="question.answer = index" :class="{selected: question.answer == index}">
				{{answer}}
			</div>
		</div>
	</div>
</template>
<script>
export default {
	props: ['question']
}
</script>
<style >
	.selected {
		background-color: red;
	}
</style>