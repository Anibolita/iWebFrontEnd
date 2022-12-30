<script>

export default{
    data: function(){
        return{
            busqueda : " ",
            token: localStorage.getItem('Token')
        };
    }
};

</script>


<template>
 
    <div>
        <h1>The Good House</h1>
        <h3>Bienvenido a The Good House, su pagina de reservas de confianza</h3>
    </div>

    <div class="buscar">
        <input v-model="busqueda" placeholder="Busque su primera vivienda" />
        <router-link :to="{ name: 'ListaViviendasLocalidad', params: { localidad: busqueda  }}" ><a class="boton_personalizado" href="">Buscar</a></router-link>
    </div>

    <table class="tabla-Inicio">    
        <tr v-if="token">
            <td class="text-button"><router-link to="/crearAnuncio" ><a class="boton_personalizado">Crear anuncio</a></router-link></td>
            <td class="text-cell">Describir la creacion de un anuncio</td>
        </tr>

        <tr>
            <td class="text-cell">Describir lo que hay en ver anuncios</td>
            <td class="text-button"><router-link to="/listaViviendas" ><a class="boton_personalizado" href="">Ver anuncios</a></router-link></td>
        </tr>

        <tr>
            <td class="text-button"><router-link to="/verTiempo" ><a class="boton_personalizado" href="">Consultar tiempo</a></router-link></td>
            <td class="text-cell">Describir lo que hace el boton de ver el tiempo</td>
        </tr>

    </table>

</template>

<style setup>
@import '../assets/componenteHomeStyle.css';
</style>