<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
    <b-form class="formulario">
      <b-row class="my-1">
        <b-col sm="3">
          <label for="Materia">Materia</label>
        </b-col>
        <b-col sm="3">
          <b-form-input type="text" v-model="nuevaMateria" placeholder="Escribe la materia inscribir"></b-form-input>
        </b-col>
      </b-row>
      
      <b-row class="my-1">
        <b-col sm="3">
          <label for="Codigo">Codigo</label>
        </b-col>
        <b-col sm="3">
          <b-form-input type="number" v-model="nuevoCodigo" placeholder="Escribe el codigo de la materia"></b-form-input>
        </b-col>
      </b-row>

      <b-row class="my-1">
        <b-col sm="3">
          <label for="Codigo">Codigo</label>
        </b-col>
        <b-col sm="3">
          <b-form-input type="text" v-model="nuevoDocente" placeholder="Escribe el nombre del docente"></b-form-input>
        </b-col>
      </b-row>

    </b-form>
    
    <b-button variant="outline-primary" v-on:click="agregarDato()">Agregar Materias</b-button>


    <!--Mostrar contenido en una tabla-->
    <b-table striped hover :items="arreglo"></b-table>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
      arreglo:[
                    {codigo:5, materia: 'Metodos de investigacion', docente:'Xiomara de Duarte'},
                    {codigo:10, materia: 'Adm. Base de datos', docente:'Edwin Trejo'},
                ],
                nuevaMateria:'',
                nuevoCodigo:'',
                nuevoDocente:''
    }
  },
  methods:{
      agregarDato(){
                    this.arreglo.push({
                         codigo: this.nuevoCodigo, materia: this.nuevaMateria, docente:this.nuevoDocente
                    });
                }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.formulario{
  margin: 30px;
}
.my-1{
  padding: 5px;
}
button{
  margin-bottom: 20px;
}

</style>
