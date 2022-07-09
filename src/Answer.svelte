<script>
    export let answerText;
    export let checkAnswerHandler;
</script>

<style>
    .Answer {

    }
</style>

<button class="Answer" on:click="{checkAnswerHandler(answerText)}">
    {answerText}
</button>