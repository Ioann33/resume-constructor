<template>
  <form class="card card-w30">
    <AppSelect
        :title="selectTitle"
        :options="data.options"
        v-model:value="selectValue"
    ></AppSelect>
    <AppTextArea
        :title="textTitle"
        v-model:value="textValue"
    ></AppTextArea>
    <AppButton
        :classes="buttonClass"
        @action="submit"
    >
      <slot name="button"></slot>
    </AppButton>
  </form>
</template>

<script>
import AppButton from "@/components/Elements/AppButton.vue";
import AppTextArea from "@/components/Elements/AppTextArea.vue";
import AppSelect from "@/components/Elements/AppSelect.vue";

export default {
  name: "AppMainForm",
  components: {AppSelect, AppTextArea, AppButton},
  data() {
    return {
      selectValue: Object.keys(this.data.options)[0] ?? '',
      textValue: ''
    }
  },
  props: {
    data: Object,
    selectTitle: String,
    textTitle: String,
    buttonClass: [Object,Array,String]
  },
  emits:['submit'],
  methods: {
    submit() {
      this.$emit('submit', this.selectValue, this.textValue)
    }
  }
}
</script>

<style scoped>

</style>