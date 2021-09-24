<template>
  <div class="Usuarios">
    <navbar></navbar>
    <tablaUsuarios></tablaUsuarios>
  </div>
</template>

<script>
import navbar from "@/components/navbar.vue";
import tablaUsuarios from "@/components/tablaUsuarios.vue";
export default {
  name: "Usuarios",
  components: {
    navbar,
    tablaUsuarios,
  },
  data() {
    return {};
  },
};
</script>

<style scoped></style>
