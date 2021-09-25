<template>
  <div class="navbar">
    <v-app-bar color="cyan" height="100px" fixed elevate-on-scroll class="">
      <v-row class="mx-auto">
        <v-btn x-large text color="white" depressed plain href="/Home"> Home </v-btn>
        <v-btn x-large text color="white" depressed plain href="/Usuarios">
          Usuarios
        </v-btn>
        <v-spacer></v-spacer>              
        <v-avatar
        class="mt-1"
        color="primary"
        size="42">
         <span class="white--text text-h8">AN</span>
        </v-avatar>        
        <v-btn        
        text
        color="white"
        x-large
        @click="logOut()"
        >      
          {{userInfo.nombreCompleto}}
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
      userInfo: [],
    };
  },
  components: {},
  methods: {
    getUserData(){
      const user = JSON.parse(window.sessionStorage.getItem("user"));
      this.userInfo = user;
      console.log(this.userInfo);
    },
    logOut(){
      window.sessionStorage.removeItem("key")
      window.sessionStorage.removeItem("user")
      this.$router.push({ name: "Login" }); 
    },
  },
  mounted(){
    this.getUserData();
  }
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
