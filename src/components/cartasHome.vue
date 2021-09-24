<template>
  <div class="cartasHome">
    <v-container fluid>
      <v-row class="mt-4">
        <v-col cols="8">
          <v-row>
            <v-col cols="6">
              <v-card elevation="4" outlined min-height="170px">
                <div class="titulo-tar margen-iz">CLIMA</div>

                <v-divider class="mt-1 mx-3 color-linea"></v-divider>
                <v-card-text class="mx-auto">
                  <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Repellendus doloremque deserunt dolores qui enim autem
                  </p>
                </v-card-text>
              </v-card>
            </v-col>
            <v-col cols="6">
              <v-card elevation="4" outlined min-height="170px">
                <div class="titulo-tar margen-iz">TITULO TARJETA</div>

                <v-divider class="mt-1 mx-3 color-linea"></v-divider>
                <v-card-text class="mx-auto">
                  <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Repellendus doloremque deserunt dolores qui enim autem
                  </p>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>

          <v-row>
            <v-col cols="6">
              <v-card elevation="4" outlined min-height="170px">
                <div class="titulo-tar margen-iz">TITULO TARJETA</div>

                <v-divider class="mt-1 mx-3 color-linea"></v-divider>
                <v-card-text class="mx-auto">
                  <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Repellendus doloremque deserunt dolores qui enim autem
                  </p>
                </v-card-text>
              </v-card>
            </v-col>
            <v-col cols="6">
              <v-card elevation="4" outlined min-height="170px">
                <div class="titulo-tar margen-iz">TITULO TARJETA</div>

                <v-divider class="mt-1 mx-3 color-linea"></v-divider>
                <v-card-text class="mx-auto">
                  <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Repellendus doloremque deserunt dolores qui enim autem
                  </p>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>

          <v-row>
            <v-col cols="6">
              <v-card elevation="4" outlined min-height="170px">
                <div class="titulo-tar margen-iz">TITULO TARJETA</div>

                <v-divider class="mt-1 mx-3 color-linea"></v-divider>
                <v-card-text class="mx-auto">
                  <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Repellendus doloremque deserunt dolores qui enim autem
                  </p>
                </v-card-text>
              </v-card>
            </v-col>
            <v-col cols="6">
              <v-card elevation="4" outlined min-height="170px">
                <div class="titulo-tar margen-iz">TITULO TARJETA</div>

                <v-divider class="mt-1 mx-3 color-linea"></v-divider>
                <v-card-text class="mx-auto">
                  <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Repellendus doloremque deserunt dolores qui enim autem
                  </p>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-col>

        <v-col cols="4">
          <v-card elevation="2" outlined min min-height="559px">
            <div class="titulo-tar margen-iz">Paises Disponibles</div>
            <v-divider class="mt-1 mx-3 color-linea"></v-divider>
            <v-row>
              <v-col cols="6">
                <v-img>

                </v-img>
              </v-col>
              <v-col cols="6">
                <v-btn
                text
                @click="getData('Mexico')"
                >
                  Meixco
                </v-btn>
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="6">
                <v-img>
                  
                </v-img>
              </v-col>
              <v-col cols="6">
                <v-btn
                 text
                 @click="getData('Canada')"
                >
                  Canada
                </v-btn>
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="6">
                <v-img>
                  
                </v-img>
              </v-col>
              <v-col cols="6">
                <v-btn
                text
                @click="getData('usa')"
                >
                  USA
                </v-btn>
              </v-col>
            </v-row>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "cartasHome",
  components: {},
  data() {
    return {};
  },
  methods:{
    getData(city) {
      fetch("https://api.weatherapi.com/v1/timezone.json?key=0aa62ac6ab564f0899811732212409&q=" + city)
      .then(response => response.json())
      .then(data => console.log(data))
    }
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300&display=swap");

.titulo {
  font-family: "Poppins";
  font: weight 700px;
  font-size: 28px;
  line-height: 40px;
  color: black;
  text-align: center;
}
.titulo-tar {
  font-family: "Poppins";
  font-size: 20px;
  text-align: left;
  color: rgba(0, 0, 0, 0.4);
}
p {
  text-align: justify;
}
.linea {
  width: 200px;
  height: 0px;
  border: 2px solid #495167;
  opacity: 1;
}
.color-linea {
  background-color: cyan;
}
.color-fondo {
  background-color: blueviolet;
}
.margen-iz {
  margin-top: 12px;
  margin-left: 20px;
}
</style>
