<script setup>
import { ref, reactive } from "vue";
import MyButton from "./MyButton.vue";

let selectedIndex = ref(null);
let menu = reactive([
  {
    id: 1,
    label: "lien 1",
    link: "/lien-1",
  },
  {
    id: 2,
    label: "lien 2",
    link: "/lien-2",
  },
  {
    id: 3,
    label: "lien 3",
    link: "/lien-3",
  },
]);
const handleClick = (item) => {
  selectedIndex.value = item.id;
};
</script>

<template>
  <ul class="menu">
    <li class="menu__item" v-for="item in menu" :key="item.id">
      <a
        :class="`menu__link ${selectedIndex === item.id ? '-active' : ''}`"
        :href="item.link"
        @click.prevent="handleClick(item)"
        >{{ item.label }}</a
      >
    </li>
  </ul>
  <MyButton type="secondary">Mon Bouton</MyButton>
</template>

<style lang="scss" scoped>
.menu {
  list-style: none;
  margin: 0;
  display: flex;
  padding: 1rem;
  &__link {
    display: inline-block;
    padding: 0.15rem 0.5rem;
    margin: 0.5rem;
    color: inherit;
    text-decoration: none;
    border-bottom: 1px solid white;
    &.-active {
      background: white;
      color: $primaryColor;
    }
  }
}
</style>
