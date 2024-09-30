<template>
  <div class="container column">
    <AppMainForm
        :data="{options: options}"
        select-title="Тип блока"
        text-title="Значение"
        button-class="primary"
        @submit="addPart"
    >
      <template v-slot:button>Добавить</template>
    </AppMainForm>
    <div class="card card-w70">
      <h3 v-if="parts.length === 0">Добавьте первый блок, чтобы увидеть результат</h3>
      <component :is="part.type" v-for="part in parts">{{part.content}}</component>
    </div>
  </div>
</template>

<script>
import AppSelect from "@/components/Elements/AppSelect.vue";
import AppTextArea from "@/components/Elements/AppTextArea.vue";
import AppButton from "@/components/Elements/AppButton.vue";
import ResumeTitle from "@/components/ResumeParts/ResumeTitle.vue";
import ResumeAvatar from "@/components/ResumeParts/ResumeAvatar.vue";
import ResumeSubtitle from "@/components/ResumeParts/ResumeSubtitle.vue";
import ResumeContent from "@/components/ResumeParts/ResumeContent.vue";
import AppLoader from "@/components/Elements/AppLoader.vue";
import AppComment from "@/components/Blocks/AppComment.vue";
import AppMainForm from "@/components/Blocks/AppMainForm.vue";

export default {
  name: 'App',
  components: {
    AppMainForm,
    AppComment,
    AppLoader,
    ResumeContent,
    ResumeSubtitle,
    ResumeAvatar,
    ResumeTitle,
    AppButton,
    AppTextArea,
    AppSelect
  },
  data(){
    return {
      options: {
        'ResumeTitle': 'Заголовок',
        'ResumeSubtitle': 'Подзаголовок',
        'ResumeAvatar': 'Аватар',
        'ResumeContent': 'Текст'
      },
      parts: [

      ]
    }
  },
  methods: {
    addPart(component, content){
      this.parts.push({
        type: component,
        content: content
      })
    }
  }
}
</script>

<style>

</style>
