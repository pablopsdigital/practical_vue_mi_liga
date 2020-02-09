<template>
  <div id="app">
    <b-container>
      <b-row>
        <!--Cargamos las tarjetas con los datos-->
        <b-col v-for="(equipo, index) in equipos" :key='index'>
          <Equipo :info="equipo"/>
        </b-col>
      </b-row>
    </b-container>

  </div>
</template>

<script>
import Equipo from './components/Equipo'

export default {
  name: 'App',
  components: {
    Equipo
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
        {
          nombre:'Equipo 5',
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
</style>
