<template>
  <div class="Home">
    <navbar></navbar>
    <cartasHome></cartasHome>
  </div>
</template>

<script>
import navbar from "@/components/navbar.vue";
import cartasHome from "@/components/cartasHome.vue";
export default {
  name: "Home",
  components: {
    navbar,
    cartasHome,
  },
  data() {
    return {};
  },
  methods: {},
  created() {},
};
</script>

<style scoped></style>
