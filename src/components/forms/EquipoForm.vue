<template>

    <b-modal id="miVentana" title="Nuevo equipo" footer-class="miventana-footer" body-class="miventana-body"
    ref='miVentana' content-class="shadow">
        
        <!--@submit y @reset para cargar métodos-->
        <b-form @submit="onSubmit" @reset="onReset" v-if="show">
            <b-form-group label="Nombre" description="Escribe el nombre del equipo">
                <b-form-input v-model="form.nombre" required placeholder='Nombre de equipo'></b-form-input>
            </b-form-group>
            <b-form-group label="Logo" description="Escribe la url de la imagen">
                <b-form-input v-model="form.logo" required placeholder='Escribe una url'></b-form-input>
            </b-form-group>
            <b-form-group label="Jugadores" description="Selecciona uno o varios jugadores">
                <b-form-select :options="jugadores" required multiple v-model="form.jugadores"></b-form-select>
            </b-form-group>
            <b-form-group>
                <b-form-radio-group v-model="form.estado">
                    <b-form-radio value="false">Inactivo</b-form-radio>
                    <b-form-radio value="true">Activo</b-form-radio>
                </b-form-radio-group>
            </b-form-group>
            <div class="form-actions float-right">
                <b-button type="reset" variant="danger">Limpiar formulario</b-button>
                <b-button type="submit" variant="primary">Enviar</b-button>
            </div>
        </b-form>
          
    </b-modal>

</template>

<script>
export default {
    name: 'EquipoForm',
    data() {
        return {
            form:{
                nombre:'',
                logo:'',
                jugadores:[],
                estado:false
            },
            jugadores:[
                'Jugador 1',
                'Jugador 2',
                'Jugador 3',
                'Jugador 4',
                'Jugador 5',
            ],
            show:true
        }
    },
    methods:{
        clearForm(){
            //Limpiar valores de formulario
            this.form.nombre='';
            this.form.logo='';
            this.form.jugadores = [];
            this.form.estado = false;

            //Para iterar sobre los elementos y mostrar
            this.show=false;
            this.$nextTick(()=>{
                this.show=true;
            })
        },
        onReset(event) {
            //Prevenir la recarga de la página
            event.preventDefault()

            //Limpiar el formulario
            this.clearForm()
        },
        onSubmit(event){
            //Prevenir la recarga de la página
            event.preventDefault();

            //Mostrar alerta con datos en json
            alert(JSON.stringify(this.form));

            //Emitimos un evento para enviar datos el formulario completo
            this.$emit('eventNuevoEquipo', this.form);

            //Cerrar la ventana
            this.$refs.miVentana.hide();

            //Limpiar el formulario
            this.clearForm()
         
        },
    }
    
}
</script>

<style>
    .icon{
    margin-right: 5px;
    }

    .miventana-footer{
    display: none !important;
    }

    .miventana-body .col-form-label {
        text-align: left;
    }

    .miventana-body .text-muted {
        text-align: right;
    }

</style>