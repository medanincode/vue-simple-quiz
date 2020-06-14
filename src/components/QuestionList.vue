<template>
  <div className="quesitons">
          <Question
            v-for="(value,index) in questions" :key="index" 
            :question="value"
            v-if="current == value.id"
            v-on="$listeners"
            />
   </div>
</template>
<script>
import Question from "./Question";
export default {
  name: 'QuestionList',
  components:{
      Question
  },
  props: {
        questions: {
            type: Array
        },
        current:{
            type:Number
        }
  }
}
</script>
