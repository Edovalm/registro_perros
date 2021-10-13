<template>
    <div class="formDueños">


<fieldset>
    <legend>Formulario Registro Dueños</legend>
        <form action="">

            <label for="idDueño">id de dueños</label><br>
            <input type="text" name="idDueño" id="idDueño" v-model="dueño.idDueño"><br>

            <label for="nombre">nombre</label><br>
            <input type="text" name="nombreDueño" id="nombre_dueño" v-model="dueño.nombreDueño"><br>

            <label for="apellidos">Imagen</label><br>
            <input type="text" name="imgDueño" id="img_dueño" v-model="dueño.imgDueño"><br>

            <button type="submit" v-on:click="guardar()">Guardar</button>
            <button type="submit" v-on:click="eliminar(dueño.idDueño)">Eliminar</button>
        </form>
</fieldset>
    </div>


</template>

<script>
import axios from 'axios'

export default {
  name:'formularioDueños',
data:function (){
return{
dueño: {
idDueño:"",
nombreDueño:"",
imgDueño: ""
}
}
},
methods:{
guardar(){

axios.post('http://localhost:8080/api/dueños',this.dueño)
.then(data=>{

console.log(data);

})

},eliminar(id){

    
    axios.delete('http://localhost:8080/api/dueños/'+id)
    .then(data=>{

console.log(data);

})
//location.reload()  
}
}
}

</script>


<style scoped>

.formDueños{

text-align: center;
padding: 5%;
font-family : inherit;

}



</style>