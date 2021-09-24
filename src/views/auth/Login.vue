<template>
  <body>
    <div class="degradado"></div>
    <div class="center">
      <h1 style="color: #00bcd4">Bienvenido</h1>
      <v-card class="mx-auto px-6" max-width="500" elevation="0">
        <v-window v-model="$store.state.loginStep">
          <v-window-item :value="0">
            <p class="mt-6 titulo">Login</p>
            <v-form class="">
              <v-text-field
                prepend-icon="mdi-account"
                label="Correo Electronico"
                type="text"
                class=""
              >
              </v-text-field>
              <v-text-field
                prepend-icon="mdi-lock"
                label="Contraseña"
                type="password"
              >
              </v-text-field>
            </v-form>

            <v-card-actions class="mb-6 mt-4">
              <v-btn raised block outlined color="blue" elevation="6">
                INICIAR SESION
              </v-btn>
            </v-card-actions>

            <v-row class="" justify-sm="center">
              <v-col class="" cols="12" xl="8" lg="8" md="8" sm="12" xs="12">
                <v-card-text> ¿No tienes una cuenta? </v-card-text>
              </v-col>
              <v-col class="" cols="12" xl="4" lg="4" md="4" sm="12" xs="12">
                <v-card-actions>
                  <v-btn
                    depressed
                    text
                    color="cyan"
                    @click="$store.state.loginStep = 1"
                  >
                    Registrarme
                  </v-btn>
                </v-card-actions>
              </v-col>
            </v-row>
          </v-window-item>
          <v-window-item :value="1">
            <p class="mt-6 titulo">Crear una cuenta</p>
            <v-text-field
              prepend-icon="mdi-account"
              label="Correo Electronico"
              type="text"
              class=""
            >
            </v-text-field>
            <v-row class="">
              <v-col
                class="mb-0 pb-0"
                cols="12"
                xl="6"
                lg="6"
                md="6"
                sm="12"
                xs="12"
              >
                <v-text-field
                  prepend-icon="mdi-lock"
                  label="Contraseña"
                  type="password"
                >
                </v-text-field>
              </v-col>
              <v-col class="" cols="12" xl="6" lg="6" md="6" sm="12" xs="12">
                <v-text-field
                  prepend-icon="mdi-lock"
                  label="Confirmar Contraseña"
                  type="password"
                >
                </v-text-field>
              </v-col>
            </v-row>
            <v-text-field
              prepend-icon="mdi-account"
              label="Nombre Completo"
              type="text"
              class=""
            >
            </v-text-field>
            <v-card-actions class="mb-6 mt-4">
              <v-btn block outlined color="blue" elevation="6">
                REGISTRARME
              </v-btn>
            </v-card-actions>
            <v-row justify="center" justify-sm="center">
              <v-card-actions class="mt-0 pt-0">
                <v-btn
                  depressed
                  text
                  color="cyan"
                  @click="$store.state.loginStep = 0"
                >
                  <v-icon left> mdi-arrow-left-bold </v-icon>
                  Ya tengo una cuenta
                </v-btn>
              </v-card-actions>
            </v-row>
          </v-window-item>
        </v-window>
      </v-card>
    </div>
  </body>
</template>

<script>
export default {
  name: "login",
  components: {},
  data() {
    return {};
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@900&display=swap");

body {
  margin: 0;
  padding: 0;
  background: url("../../assets/media/backgrounds/nubes-copia.png");
  height: 100vh;
  overflow: hidden;
}
.degradado {
  background: linear-gradient(
    to right bottom,
    #081f42,
    #00276c,
    #002b96,
    #0628bd,
    #8d5cff
  );
  height: 100vh;
  opacity: 0.6;
}
.titulo {
  font: weight 700px;
  font-size: 30px;
  text-align: left;
}

@media screen and (min-width: 800px) {
  .center {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 550px;
    height: 600px;
    background: white;
    border-radius: 20px;
    box-shadow: 10px 10px 15px rgba(0, 0, 0, 0.05);
  }
}
@media screen and (max-width: 800px) {
  .center {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 400px;
    height: 600px;
    background: white;
    border-radius: 10px;
    box-shadow: 10px 10px 15px rgba(0, 0, 0, 0.05);
  }
}

.center h1 {
  text-align: center;
  padding: 20px 0;
  border-bottom: 1px solid silver;
}
</style>
