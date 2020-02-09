<template>
  <div id="app">

    <b-container>
      <b-row>
        <b-col>
          <b-button v-b-modal="'miVentana'" variant="success" class="float-right new-btn">
            <v-icon class="icon" name='plus'/>
            Agregar Equipo
          </b-button>
        </b-col>
      </b-row>

      <b-row>
        <!--Cargamos las tarjetas con los datos-->
        <b-col v-for="(equipo, index) in equipos" :key='index'>
          <Equipo :info="equipo"/>
        </b-col>
      </b-row>
    </b-container>

    <!--Escucha metodo eventNuevoEquipo que lanza el componente-->
    <EquipoForm @eventNuevoEquipo="crearNuevoEquipo"/>

  </div>
</template>

<script>
import Equipo from './components/Equipo'
import EquipoForm from './components/forms/EquipoForm'

export default {
  name: 'App',
  components: {
    Equipo,
    EquipoForm
  },
  data(){
    return{
      equipos:[
        {
          nombre:'Equipo 1',
          logo: "https://via.placeholder.com/600x300/D2B48C/ffffff?text=Logo+equipo",
          estado:true,
          jugadores:[
              {jugador:'1'},
              {jugador:'2'},
              {jugador:'3'},
          ]
        },
        {
          nombre:'Equipo 2',
          logo: "https://via.placeholder.com/600x300/D2B48C/ffffff?text=Logo+equipo",
          estado:true,
          jugadores:[
              {jugador:'1'},
              {jugador:'2'},
              {jugador:'3'},
          ]
        },
        {
          nombre:'Equipo 3',
          logo: "https://via.placeholder.com/600x300/D2B48C/ffffff?text=Logo+equipo",
          estado:true,
          jugadores:[
              {jugador:'1'},
              {jugador:'2'},
              {jugador:'3'},
          ]
        },
        {
          nombre:'Equipo 4',
          logo: "https://via.placeholder.com/600x300/D2B48C/ffffff?text=Logo+equipo",
          estado:true,
          jugadores:[
              {jugador:'1'},
              {jugador:'2'},
              {jugador:'3'},
          ]
        },
      ]
    }
  },
  methods:{
    //Método que llama el componente
    crearNuevoEquipo(equipo){
      //Agregamos al array equipo el nuevo equipo
      //Para no tener instancias iguales usamos Object.assign
      this.equipos.push(Object.assign({},equipo));
    }
  }
}
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  .new-btn{
    margin-bottom: 20px;
  }
</style>
