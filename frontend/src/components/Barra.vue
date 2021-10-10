<template>
  <v-card class="overflow-hidden">
    <v-app-bar
      
      color="#6A76AB"
      dark
      shrink-on-scroll
      prominent
      src="https://lh3.googleusercontent.com/JJY3JlqHayuFFFZYAoyp1MFnUtFRIqdGhRSoAMY42PB2bmcgHp9iPlbd-NRDxW544gTpDg=s170"
      fade-img-on-scroll
      scroll-target="#scrolling-techniques-3"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"
        ></v-img>
      </template>

      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-app-bar-title>APP NOTAS   . </v-app-bar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon></v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon></v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon></v-icon>
      </v-btn>

      <template v-slot:extension>
        <v-tabs align-with-title>
          <v-tab @click="llamarRegistro()">Realizar un registro</v-tab>
          <v-tab @click="llamarTabla()">Reportes</v-tab>
          
        </v-tabs>
      </template>
    </v-app-bar>
    <v-sheet
      id="scrolling-techniques-3"
      class="overflow-y-auto"
      max-height="600"
    >
      
    </v-sheet>
  </v-card>
</template>

<script>
export default {
    data() {
        
    },

    methods:{

        llamarRegistro(){

            this.$router.push('/registro')


        },

           llamarTabla(){

            this.$router.push('/tabla')


        },

         llamarCarrusel(){

            this.$router.push('/carrusel')


        }



    }
}
</script>


