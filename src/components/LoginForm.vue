<template>
  <v-window v-model="$store.state.loginStep">
    <v-window-item :value="0">
      <h1>Login</h1>
      <v-btn @click="$store.state.loginStep = 1"> Registrarme </v-btn>
    </v-window-item>
    <v-window-item :value="1">
      <h1>Register</h1>
      <v-btn @click="$store.state.loginStep = 0"> Iniciar Sesion </v-btn>
    </v-window-item>
  </v-window>
</template>

<script>
export default {
  name: "login",
  data() {
    return {};
  },
};
</script>

<style scoped></style>
