<script>
import MyButton from "./MyButton.vue";
export default {
  components: {
    MyButton,
  },
  data() {
    return {
      hasError: false,
      email: "",
      password: "",
      cgv: false,
    };
  },
  methods: {
    handleSubmit() {
      if (this.email.length === 0 && this.password.length === 0) {
        this.hasError = true;
      }
    },
  },
};
</script>

<template>
  <form @submit.prevent="handleSubmit">
    <div>
      <input v-model="email" type="text" />
    </div>
    <div>
      <input v-model="password" type="text" />
    </div>
    <div>
      <input v-model="cgv" type="checkbox" name="cgv" />
      <label for="cgv">J'accepte les CGV</label>
    </div>
    <div v-if="hasError === true">Il manque des informations !</div>
    <div v-else>C'est okay !</div>
    <MyButton>Submit</MyButton>
  </form>
</template>
