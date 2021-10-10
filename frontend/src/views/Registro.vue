<template>
<v-container>
  <v-form @submit.prevent="agregarEstudiante()">


    <v-text-field
      v-model="atributos.nombre"
      :counter="30"
      label="Nombre del estudiante"
    ></v-text-field>


    <v-select
      v-model="atributos.materia"
      :items="Materias"
      label="Materia"
      required
    ></v-select>

    <v-text-field
      v-model="atributos.nota"
      label="Nota"
    ></v-text-field>


    <v-btn
      color="success"
      class="mr-4"
      type="submit"
    >
      Enviar registro
    </v-btn>

    <!-- <v-btn
      color="error"
      class="mr-4"
      @click="limpiar()"
    >
      Limpiar
    </v-btn> -->


  </v-form>
  </v-container>
</template>

<script>
export default {

data(){

  return {
    Atributos:[],

    atributos: {

      nombre:"",
      materia:"",
      nota:"",

    },

    Materias:['Matematicas','Sociales', 'Ingles', 'Filosofia', 'Ciencias Politica']


  }


},

methods:{


  agregarEstudiante(){
  console.log(this.atributos);
    if(!this.atributos.nombre){

      this.$swal('Error!',
                    'Falta Nombre del estudiante!',
                    'error');


    }

    else if(!this.atributos.materia){

      this.$swal('Error!',
                    'Falta materia del estudiante!',
                    'error');




    }

    else if(!this.atributos.nota){

      this.$swal('Error!',
                    'Falta nota del estudiante!',
                    'error');


    }

  

    else{

      this.axios
    .post("/nuevo-registro",this.atributos)
    .then((res)=>{
      this.Atributos.push(res.data);


      this.$swal('success!',
                    'estudiante Agregado exitosamente!',
                    'success');
    
    

      
      
      this.atributos.nombre="";
      this.atributos.materia="";
      this.atributos.nota="";

  
    })

    .catch((e)=>{

      console.log(e.response);

      alert("Error en guardar registro");


    })


    }

  
    
    

  },



  






}

  
}
</script>