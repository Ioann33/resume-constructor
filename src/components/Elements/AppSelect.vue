<template>
  <div class="form-control">
    <label :for="id">{{title}}</label>
    <select :id="id">
      <option :value="i" v-for="(option, i) in options">{{option}}</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "AppSelect",
  data () {
    return {
      id: 'select-' + Math.random()
    }
  },
  props: {
    title: String,
    options: Object
  }
}
</script>

<style scoped>

</style>