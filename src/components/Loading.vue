<template>
    <div class="loading">
        <span v-bind:style="{width: percent + '%' }"></span>
    </div>
</template>

<script>
export default {
  name: 'Loading',
  props: {
        percent: {
            type: Number
        }
    }
}
</script>
