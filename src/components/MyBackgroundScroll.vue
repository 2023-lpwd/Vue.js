<script>
export default {
  data() {
    return {
      percent: 0,
    };
  },
  methods: {
    handleScroll() {
      let scrollTop = window.scrollY;
      let scrollBottom = scrollTop + window.innerHeight;
      let elementTop = this.$refs.container.offsetTop;
      let elementHeight = this.$refs.container.offsetHeight;
      let percent = Math.round(
        ((scrollBottom - elementTop) / elementHeight) * 100
      );
      this.percent = percent < 100 ? percent : 100;
    },
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll, { passive: true });
  },
  unmounted() {
    window.removeEventListener("scroll", this.handleScroll);
  },
};
</script>

<template>
  <div ref="container" class="background">
    <div class="background__content">
      {{ percent }}
    </div>
  </div>
</template>

<style lang="scss" scoped>
.background {
  height: 2000px;
  background: black;
  color: white;
  position: relative;
  &__content {
    position: sticky;
    left: 0;
    top: 0;
    width: 100%;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 3rem;
  }
}
</style>
