<script>
	import Question from 'Question.svlete';
	import Answer from 'Answer.svelte';
	import Points from 'Points.svelte';

	let currentQuestion = 0;

	const quiz = [
		{
			question: 'Is the sky blue?',
			correctAnswer: 0,
			answer: [
				'Yes',
				'No'
			]
		},
		{
			question: 'Is grass purple?',
			correctAnswer: 1,
			answer: [
				'Yes',
				'No'
			]
		}
	]
</script>

<style>
</style>

<div class="App">
	<Question/>
	<div class="answers">
		<Answer/>
		<Answer/>
	</div>
</div>