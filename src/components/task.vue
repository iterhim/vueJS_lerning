<template>
    {{ task }}
    <button type="button" v-if="task" v-on:click="$emit('remove') ">done</button>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Task",
  data() {
    return {
      text: 'asd'
    }
  },
  props: {
    task: String,
  },

  methods: {

  }
}
</script>

<style scoped>

</style>