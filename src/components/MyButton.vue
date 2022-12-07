<script>
export default {
  data() {
    return {
      className: `button ${this.type === "secondary" ? "-secondary" : ""}`,
    };
  },
  props: {
    href: String,
    type: String,
  },
};

// Si type === "secondary" => class="button"
</script>

<template>
  <a v-if="href" :href="href" :class="className">
    <slot></slot>
  </a>
  <button v-else :class="className">
    <slot></slot>
  </button>
</template>

<style lang="scss" scoped>
@import "./../scss/foundations/variables";
$backgroundColor: $primaryColor;
$color: white;
.button {
  padding: 1rem;
  display: inline-block;
  background-color: $backgroundColor;
  color: $color;
  text-decoration: none;
  border: 1px solid $backgroundColor;
  border-radius: 5px;
  font-size: 1rem;
  line-height: 1rem;
  font-family: $textFontFamily;
  margin: 0.5rem;
  cursor: pointer;
  &:hover {
    color: $backgroundColor;
    background: transparent;
  }
  &.-secondary {
    color: $backgroundColor;
    background-color: $color;
    &:hover {
      background-color: $backgroundColor;
      color: $color;
    }
  }
}
</style>
