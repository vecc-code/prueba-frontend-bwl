<template>
  <div class="navbar">
    <v-app-bar color="cyan" height="100px" fixed elevate-on-scroll class="">
      <v-row class="mx-auto">
        <v-btn x-large color="white" depressed plain href="/Home"> Home </v-btn>
        <v-btn x-large color="white" depressed plain href="/Usuarios">
          Usuarios
        </v-btn>
      </v-row>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  name: "navbar",
  data() {
    return {
      texto: "",
    };
  },
  components: {},
  methods: {},
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@500&display=swap");
.navbar {
  display: block;
  height: 100px;
  width: 100%;
}
</style>

<style scoped>
.btn-selected {
  color: #000000 !important;
}
.tab {
  color: #000000;
  font-size: 18px;
  font-family: "Poopins", sans-serif;
}
</style>
