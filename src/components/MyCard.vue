<script>
export default {
  props: {
    title: String,
    srcImage: String,
  },
};
</script>
<template>
  <div class="card">
    <div class="card__image">
      <img :src="srcImage" :alt="title" />
    </div>
    <p class="card__title">{{ title }}</p>
  </div>
</template>

<style lang="scss" scoped>
.card {
  max-width: 200px;
  border-radius: 5px;
  padding: 1rem;
  -webkit-box-shadow: 5px 5px 16px -7px #dadada;
  box-shadow: 5px 5px 16px -7px #dadada;
}
</style>
