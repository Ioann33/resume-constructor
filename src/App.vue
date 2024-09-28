<template>
  <div class="container column">
    <form class="card card-w30">
      <AppSelect
          title="Тип блока"
          :options="options"
      ></AppSelect>
      <AppTextArea
          title="Значение"
      ></AppTextArea>
      <AppButton
          classes="primary"
      >Добавить</AppButton>
    </form>

    <div class="card card-w70">
      <ResumeTitle>Резюме Nickname</ResumeTitle>
      <ResumeAvatar
          url="https://cdn.dribbble.com/users/5592443/screenshots/14279501/drbl_pop_r_m_rick_4x.png"
      ></ResumeAvatar>
      <ResumeSubtitle>Опыт работы</ResumeSubtitle>
      <ResumeContent>
        главный герой американского мультсериала «Рик и Морти», гениальный учёный, изобретатель, атеист (хотя в некоторых сериях он даже молится Богу, однако, каждый раз после чудесного спасения ссылается на удачу и вновь отвергает его существование), алкоголик, социопат, дедушка Морти. На момент начала третьего сезона ему 70 лет[1]. Рик боится пиратов, а его главной слабостью является некий - "Санчезиум". Исходя из того, что существует неограниченное количество вселенных, существует неограниченное количество Риков, герой сериала предположительно принадлежит к измерению С-137. В серии комикcов Рик относится к измерению C-132, а в игре «Pocket Mortys» — к измерению C-123[2]. Прототипом Рика Санчеза является Эмметт Браун, герой кинотрилогии «Назад в будущее»[3].
      </ResumeContent>
      <h3>Добавьте первый блок, чтобы увидеть результат</h3>
    </div>
  </div>
  <div class="container">
    <p>
      <AppButton
          classes="primary"
      >Загрузить комментарии</AppButton>
    </p>
    <div class="card">
      <h2>Комментарии</h2>
      <ul class="list">
        <li class="list-item">
          <div>
            <p><strong>test@microsoft.com</strong></p>
            <small>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi, reiciendis.</small>
          </div>
        </li>
      </ul>
    </div>
    <AppLoader></AppLoader>
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

export default {
  name: 'App',
  components: {
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
        title: 'Заголовок',
        subtitle: 'Подзаголовок',
        avatar: 'Аватар',
        text: 'Текст'
      }
    }
  }
}
</script>

<style>

</style>
