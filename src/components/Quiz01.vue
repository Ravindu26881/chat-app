<template>
<div class="quiz-one__wrapper">
  <div v-if="curruntQ === 1" class="quiz-one">
    <div class="">
      Q1 <div v-if="answers[1] != null"> Selected answer = {{answers[1]}}</div>
    </div>
    <div class="btn-group-vertical" role="group" aria-label="Basic outlined example">
      <button @click="quizAnswer(1,1)" type="button" class="btn btn-outline-primary">1</button>
      <button @click="quizAnswer(1,2)" type="button" class="btn btn-outline-primary">2</button>
      <button @click="quizAnswer(1,3)" type="button" class="btn btn-outline-primary">3</button>
    </div>
  </div>

  <div v-if="curruntQ === 2" class="quiz-one">
    <div class="">
      Q2 <div v-if="answers[2] != null"> Selected answer = {{answers[2]}}</div>
    </div>
    <div class="btn-group-vertical" role="group" aria-label="Basic outlined example">
      <button @click="quizAnswer(2,1)" type="button" class="btn btn-outline-primary">1</button>
      <button @click="quizAnswer(2,2)" type="button" class="btn btn-outline-primary">2</button>
      <button @click="quizAnswer(2,3)" type="button" class="btn btn-outline-primary">3</button>
    </div>
  </div>

  <div v-if="curruntQ === 3" class="quiz-one">
    <div class="">
      Q3 <div v-if="answers[3] != null"> Selected answer = {{answers[3]}}</div>
    </div>
    <div class="btn-group-vertical" role="group" aria-label="Basic outlined example">
      <button @click="quizAnswer(3,1)" type="button" class="btn btn-outline-primary">1</button>
      <button @click="quizAnswer(3,2)" type="button" class="btn btn-outline-primary">2</button>
      <button @click="quizAnswer(3,3)" type="button" class="btn btn-outline-primary">3</button>
    </div>
  </div>


  <div class="btn-toolbar" role="toolbar" aria-label="Toolbar with button groups">
    <div class="btn-group me-2" role="group" aria-label="First group">
      <button @click="changeQuizNumber(1)" type="button" class="btn btn-primary">1</button>
      <button @click="changeQuizNumber(2)" type="button" class="btn btn-primary">2</button>
      <button @click="changeQuizNumber(3)" type="button" class="btn btn-primary">3</button>
    </div>
  </div>

</div>
</template>

<script>
export default {
  name: 'Quiz01',
  props: {
    msg: String
  },
  data () {
    return {
      curruntQ: 1,
      answers: []
    }
  },
  methods: {
    changeQuizNumber(value) {
      this.curruntQ = value
    },
    quizAnswer (quizNumber, quizAnswer) {
      this.answers[quizNumber] = quizAnswer
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
