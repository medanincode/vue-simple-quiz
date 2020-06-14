<template>
  <div class="question">
    <h3>{{question.text}}</h3>
    <hr>
    <div class="inputGroup" v-for="(value,key) in question.choices" :key="key">
      <input @change="setCurrent"  :id="value.id"  type="radio" name="radio" :value="value.id"/>
      <label :for="value.id"> {{value.text}}</label>
    </div>
 
  </div>
</template>
<script>
export default {
  name: 'Question',
  props: {
        question: {
            type: Object
        }
  },
  methods: {
    setCurrent(e){
        setTimeout(function(){
           const selected = e.target.value;
        if(selected===this.question.correct){
          this.$emit('setScore');
        }
        this.$emit('setCurrent');
        }.bind(this),500);
        
    }
  },
}
</script>
