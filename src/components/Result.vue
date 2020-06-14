<template>
  <div class="well">
    <div className="well">
        <h4>You got {{score}} out of {{questions.length}}</h4>
        <h2>{{percent}}% - {{message}}</h2>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Results',
    props: {
        score: {
            type: Number
        },
        questions: {
            type: Array
        }
    },
    data(){
        return {
            percent:0,
            message:''
        }
    },
    mounted(){
        this.percent = (this.score / this.questions.length * 100);
        if (this.percent > 80) {
            this.message = 'You did awesome!';
        } else if (this.percent < 80 && this.percent >= 50) {
            this.message = 'You did just fine';
        } else {
            this.message = 'You did horrible, sorry';
        }
    }
}
</script>
