<template>
  <section>
    <AppLayoutHeader
      :isLoggin="isLoggin"
      @userLoggin="$emit('userLoggin')"
      @userUnLoggin="$emit('userUnLoggin')"
    />

    <div class="layout_with_sidebar">
      <div>Sidebar !!!</div>
      <slot />
    </div>
  </section>
</template>

<script>
import AppLayoutHeader from "./AppLayoutHeader.vue";
export default {
  name: "AppLayoutMain",
  components: {
    AppLayoutHeader,
  },
  props: {
    isLoggin: {
      type: Boolean,
      required: true,
    },
  },
};
</script>

<style scoped>
.layout_with_sidebar {
  display: grid;
  grid-template-columns: 30% 70%;
  column-gap: 20px;
}
</style>
