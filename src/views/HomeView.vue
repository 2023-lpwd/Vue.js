<script>
import MyButton from "./../components/MyButton.vue";
import MyTitle from "./../components/MyTitle.vue";
import MyCardList from "./../components/MyCardList.vue";
import MyBackgroundScroll from "./../components/MyBackgroundScroll.vue";
import DefaultLayout from "./../layouts/DefaultLayout.vue";
import MyFooter from "../components/MyFooterVue3.vue";
import MyForm from "../components/MyForm.vue";
export default {
  components: {
    MyButton,
    MyCardList,
    MyTitle,
    MyBackgroundScroll,
    DefaultLayout,
    MyForm,
    MyFooter,
  },
};
</script>

<template>
  <DefaultLayout>
    <template v-slot:header>
      <MyTitle label="Titre normale h3" type="h3" />
      <MyTitle size="big" label="Grand Titre h1" />
      <MyTitle size="tiny" type="h2" label="Petit Titre h2" />
    </template>
    <template v-slot:aside>
      <MyButton href="/lien">Cliquez ici !</MyButton>
      <MyButton type="secondary" size="tiny">Validez le formulaire</MyButton>
    </template>
    <MyForm />
    <MyCardList />
    <MyBackgroundScroll />
    <template v-slot:footer>
      <MyFooter />
    </template>
  </DefaultLayout>
</template>
