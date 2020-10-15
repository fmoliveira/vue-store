<template>
  <div>
    <NavBar />
    <main>
      <slot></slot>
    </main>
  </div>
</template>

<script>
import NavBar from "./NavBar.vue";

export default {
  name: "Layout",
  components: {
    NavBar,
  },
};
</script>

<style scoped>
main {
  padding: 24px;
}
</style>
