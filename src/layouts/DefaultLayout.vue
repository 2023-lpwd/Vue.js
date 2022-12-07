<script></script>

<template>
  <main class="layout">
    <header>
      <slot name="header"></slot>
    </header>
    <aside>
      <slot name="aside"></slot>
    </aside>
    <article>
      <slot></slot>
    </article>
    <footer>
      <slot name="footer"></slot>
    </footer>
  </main>
</template>

<style lang="scss" scoped>
.layout {
  display: grid;
  grid-template:
    "header"
    "article"
    "aside"
    "footer";
  @media (min-width: 600px) {
    grid-template:
      "header header header"
      "aside article article"
      "footer footer footer";
  }
  header {
    grid-area: header;
  }
  aside {
    grid-area: aside;
  }
  article {
    grid-area: article;
  }
  footer {
    grid-area: footer;
  }

  header,
  footer {
    background: $primaryColor;
    color: white;
  }
}
</style>
