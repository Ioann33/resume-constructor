<template>
  <div class="form-control">
    <label :for="id">{{title}}</label>
    <select :id="id"
            :value="value"
            @input="change">
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
    options: Object,
    value: String
  },
  methods: {
    change (event) {
      this.$emit('update:value', event.target.value)
    }
  }

}
</script>

<style scoped>

</style>