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
<!--      <ResumeTitle>Резюме Nickname</ResumeTitle>-->
<!--      <ResumeAvatar-->
<!--          url="https://cdn.dribbble.com/users/5592443/screenshots/14279501/drbl_pop_r_m_rick_4x.png"-->
<!--      ></ResumeAvatar>-->
<!--      <ResumeSubtitle>Опыт работы</ResumeSubtitle>-->
<!--      <ResumeContent>-->
<!--        главный герой американского мультсериала «Рик и Морти», гениальный учёный, изобретатель, атеист (хотя в некоторых сериях он даже молится Богу, однако, каждый раз после чудесного спасения ссылается на удачу и вновь отвергает его существование), алкоголик, социопат, дедушка Морти. На момент начала третьего сезона ему 70 лет[1]. Рик боится пиратов, а его главной слабостью является некий - "Санчезиум". Исходя из того, что существует неограниченное количество вселенных, существует неограниченное количество Риков, герой сериала предположительно принадлежит к измерению С-137. В серии комикcов Рик относится к измерению C-132, а в игре «Pocket Mortys» — к измерению C-123[2]. Прототипом Рика Санчеза является Эмметт Браун, герой кинотрилогии «Назад в будущее»[3].-->
<!--      </ResumeContent>-->
    </div>
  </div>
<!--  <AppComment></AppComment>-->
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
