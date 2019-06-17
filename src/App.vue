<template>
  <v-app id="inspire">
    <Header></Header>
    <v-content>
      <v-container fluid fill-height>
        <v-layout row wrap>
          <router-view></router-view>                   
        </v-layout>        
      </v-container>      
    </v-content>
    <Footer></Footer> 
  </v-app>
</template>

<script>
  import Footer from './components/Footer'
  import Header from './components/Header'
  export default {    
    name: "App",
    components: {
      Footer,
      Header
    },
    data: () => ({
      dialog: false,
    }),
    props: {
      source: String
    }
  }
</script>
