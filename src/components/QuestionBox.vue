<template>
<div>
  <b-jumbotron>
    <template v-slot:lead>
        {{ currentQuestion.question}}
    </template>

    <hr class="my-4">
    <b-list-group class="mb-4">
        <b-list-group-item v-for="(answer, index) in answers" :key="index">{{ answer}}</b-list-group-item>
    </b-list-group>
    <b-button class="mr-2" variant="primary" href="#">Submit</b-button>
    <b-button @click="next" variant="success" href="#">Next</b-button>
  </b-jumbotron>
</div>
</template>
<script>
export default {
    props: {
        currentQuestion: Object,
        next: Function 
    },
    computed:{
        answers(){
            let answers = [...this.currentQuestion.incorrect_answers]
            answers.push(this.currentQuestion.correct_answer)
            return answers
        }
    },
    mounted(){

    }
}
</script>

<style scoped>
</style>