<script>
  import Question from "./Question.svelte";
  import Answer from "./Answer.svelte";
  import Points from "./Points.svelte";

  let points = 0;
  let currentQuestion = 0;

  const quiz = [
    {
      question: "Is the sky blue?",
      correctAnswer: 0,
      answer: ["Yes", "No"],
    },
    {
      question: "Is grass purple?",
      correctAnswer: 1,
      answer: ["Yes", "No"],
    },
  ];

  function checkAnswerHandler(answerText) {
    const isCorrect =
      quiz[currentQuestion].answer.indexOf(answerText) ===
      quiz[currentQuestion].correctAnswer;
    if (isCorrect) {
      points += 1;
      quiz[currentQuestion].question = "Correct!";
    } else {
      quiz[currentQuestion].question = "Wrong =(";
    }
    setTimeout(() => {
      currentQuestion += 1;
    }, 2000);
  }
</script>

<div class="App">
  <div>
    <Question
      questionText={quiz[currentQuestion].question}
    />
    <div class="answers">
      <Answer
        answerText={quiz[currentQuestion].answer[0]}
        {checkAnswerHandler}
      />
      <Answer
        answerText={quiz[currentQuestion].answer[1]}
        {checkAnswerHandler}
      />
    </div>
  </div>
  
  <Points {points} />
</div>

<style>
  .App {
    display: flex;
	justify-content: space-around;
  }
</style>
