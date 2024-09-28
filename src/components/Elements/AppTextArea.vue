<template>
  <div class="form-control">
    <label :for="id">{{title}}</label>
    <textarea :id="id"
              rows="3"
              :placeholder="placeholder"
              :value="value"
              @input="change"
    ></textarea>
    <small v-if="error">{{error}}</small>
  </div>
</template>

<script>
export default {
  name: "AppTextArea",
  props: {
    value:[String, Number],
    placeholder: {
      type: String,
      default: null
    },
    title: String,
    error: {
      type: String,
      default: null
    }
  },
  emits: ['update:value'],
  data () {
    return {
      id: 'textarea-' + Math.random()
    }
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