<template>
	<div>
		<h1>Tổng điểm : {{questions.reduce( (total, ques)=>{
			if(ques.correctAnswer == ques.answer) {
				total = total + ques.point;
				
			}
			return total;
			},0) }}</h1>
		<div v-for="(ques, indexQ) in questions" :key="indexQ">
			<div>{{ques.content}}</div>
			<div v-for="(answer, index) in ques.answers" :key="index" :class="{selected: ques.answer == index , correct: ques.correctAnswer == index}">
				{{answer}}
			</div>
		</div>
	</div>
</template>
<script>
export default {
	props : ['questions']
}
</script>
<style >
	.selected {
		background-color:red;
		width: 300px;
	}
	.correct {
		background-color: blue;
		width: 300px;
	}
</style>