<template>
    <div>
    <b-card
        :header="info.nombre"
        :img-src="info.logo"
        img-alt="Equipos"
        img-top
        tag="article"
        style="max-width: 20rem;"
        class="mb-2"
    >

        <b-card-text>
            Estado:
            <!--Cargamos clase activo si estado es true y inactivo si es false!
            despues añadirmos otra clase para dar la forma de punto-->
            <div :class="{'activo':info.estado, 'inactivo':!info.estado}" class="circulo"></div>

            <!--Cargamos clase si estado activo o inactivo y forma de circulo-->
            <br>Jugadores:{{info.jugadores.length}}
        </b-card-text>

        <b-button href="#" variant="primary">Ver jugadores</b-button>
    </b-card>
    </div>
</template>

<script>
export default {
    name:'Equipo',
    props:{
        info:{
            nombre:String,
            logo:String,
            estado:Boolean,
            jugadores:Array
        }
    },
    data(){
        return{
            // nombre:'Equipo 1',
            // logo: "https://via.placeholder.com/600x300/D2B48C/ffffff?text=Logo+equipo",
            // estado:true,
            // jugadores:[
            //     {jugador:'1'},
            //     {jugador:'2'},
            //     {jugador:'3'},
            // ]
        }
    }


}
</script>

<style scoped>
.circulo{
    width: 30px;
    height: 30px;
    border-radius: 50%;
    margin: 0 auto;
}
.activo{
    background-color: green;
}
.inactivo{
    background-color: gray;
}

</style>