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
                 <v-row>
                   <v-col cols="6">
                     <v-img
                     :src="clima.current.condition.icon"
                     >
                     </v-img>                                            
                   </v-col>
                   <v-col cols="6">
                     {{clima.current.temp_c}} C <br/> {{clima.current.condition.text}}
                   </v-col>
                 </v-row>
                </v-card-text>
              </v-card>
            </v-col>
            <v-col cols="6">
              <v-card elevation="4" outlined min-height="170px">
                <div class="titulo-tar margen-iz">Pais Seleccionado</div>

                <v-divider class="mt-1 mx-3 color-linea"></v-divider>
                <v-card-text class="mx-auto">
                  <v-row>
                    <v-col cols="6">
                      {{paisName}}
                    </v-col>
                    <v-col cols="6">
                      <v-img
                      :src="paisImg"
                      >                        
                      </v-img>
                    </v-col>
                  </v-row>                
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
                <div class="titulo-tar margen-iz">Hora</div>

                <v-divider class="mt-1 mx-3 color-linea"></v-divider>
                <v-card-text class="mx-auto">
                  <p>
                    {{newHora}}
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
                <div class="titulo-tar margen-iz">Zonas Horarias</div>

                <v-divider class="mt-1 mx-3 color-linea"></v-divider>
                <v-card-text class="mx-auto">
                  <v-row>
                    <v-col cols="12"
                    v-for="(item) in timeZones.zones"
                  :key="item.id" >
                  <v-btn
                  text      
                  @click="setHorayClima(item.zoneName)"                                   
                  >
                   {{item.zoneName}} 
                  </v-btn>  
                      
                    </v-col>
                  </v-row>
                                                    
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
                @click="setPais('MX')"
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
                 @click="setPais('CA')"
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
                @click="setPais('US')"
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
    return {
      timeZones: [],
      paisName: "",
      paisImg: "",
      clima: [],
      newHora: null,
      };
  },
  mounted() {
    this.setPais("MX");
    //this.setHorayClima(this.timeZones.zones[0].zoneName); 
    
  },
  methods:{
    async getData(city) {
      let response = await fetch("http://api.timezonedb.com/v2.1/list-time-zone?key=TMTQ32PJM68R&format=json&country=" + city);
      const result = await response.json();
      this.timeZones = result;
      const name = await this.timeZones.zones[0].zoneName;
      console.log(name);      
      this.setHorayClima(name);
      

    },
    async setPais(city){
      switch (city) {
        case "MX":
          this.paisName = 'Mexico';
          this.paisImg = 'https://img2.freepng.es/20190613/ytf/kisspng-flag-of-mexico-united-states-national-flag-5d02ebbe376f35.6418073615604725102271.jpg';
          break;
        case "CA":
          this.paisName = 'Canada';
          this.paisImg = '';
          break;
          case "US":
          this.paisName = 'US';
          this.paisImg = '';
          break;          
      }
      this.getData(city);
    },
    async setHorayClima(nombreDeZona){
      console.log("http://api.weatherapi.com/v1/current.json?key=0aa62ac6ab564f0899811732212409&q&q=" +nombreDeZona +"&aqi=no");
      let response = await fetch("https://api.weatherapi.com/v1/forecast.json?key=0aa62ac6ab564f0899811732212409&q&q&q="+nombreDeZona+"&days=1&aqi=no&alerts=yes");      
      this.clima = await response.json();
      console.log(this.clima.current.temp_c);       
      this.setHoraReal(nombreDeZona);
    },
    async setHoraReal(nombreDeZona){
      let response = await fetch("https://api.weatherapi.com/v1/timezone.json?key=0aa62ac6ab564f0899811732212409&q&q&q="+nombreDeZona);
      this.hora = await response.json();
      console.log(new Date(this.hora.location.localtime_epoch).toLocaleTimeString());
      this.newHora = new Date(this.hora.location.localtime_epoch).toLocaleTimeString();
    },
    
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
