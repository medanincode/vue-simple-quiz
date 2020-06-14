<template>
  <div class="well">
     Question {{current}} out of {{questions.length}}
  </div>
</template>

<script>
export default {
  name: 'BoxScore',
  props: {
        current: {
            type: Number
        },
        questions: {
            type: Array
        }
    }
}
</script>
