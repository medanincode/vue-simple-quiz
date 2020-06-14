<template>
  <div id="app">
    <div id="header">
    Vue Simple Quiz by <a class="text-red" href="https://medanincode.com">MedanInCode</a>
    </div>
    <div v-if="current > questions.length">
      <a href="" class="btn-retry">Take Quiz Again</a>
      <Result
        :score="score"
        :questions="questions"
      />
    </div>
    <div v-else>
      <Loading
        :percent="((current-1) * (100/questions.length))"
      />
      <BoxScore 
      :current="current"
      :questions="questions"
      />
      <QuestionList
        :questions="questions"
        :current="current"
        @setCurrent="setCurrent"
        @setScore="setScore"
      />
    </div>
  </div>
</template>

<script>
import BoxScore from './components/BoxScore'
import Result from './components/Result'
import QuestionList from './components/QuestionList'
import Loading from './components/Loading'
//question
import questions from "./questions";
export default {
  name: 'App',
  components: {
    BoxScore,
    Result,
    QuestionList,
    Loading
  },
  data () {
    return {
      questions:questions,
      score: 0,
      current: 1
    }
  },
  methods: {
    setCurrent(){
      this.current +=1;
    },
    setScore(){
      this.score +=1;
    }
    
  }
}
</script>
