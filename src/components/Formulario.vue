<template>

  <section class="src-components-formulario">
    <h1>Recuperatorio</h1>
    <label for="texto">Texto a ingresar</label>
    
 

    <input type="text" v-model="texto" @input="actualizar()"> <br>
    <hr>
    <p>{{ todoMayuscula }} , todo mayuscula </p>
    <p>{{ todoMinuscula }} , todo minuscula </p>
    <p>{{ codificado }} , codificado </p>
     <p>{{ mayusculaMinuscula }} , Mayuscula-Minuscula</p>
      <p>{{ minusculaMayuscula }} , Minuscula-Mayuscula</p>
    <p>cantidad, {{contar}} </p>

    <hr>
    <br>
    <p>Respuestas:</p>
    <p>1:c , 2:b, 3:c, 4:a , 5:c</p>  
  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-components-formulario',
    props: [],
    mounted () {

    },
    data () {
      return {
        texto:'',
        todoMayuscula:'',
        todoMinuscula:'',
        total:'',
        mayusculaMinuscula:'',
        minusculaMayuscula:'',
        codifica:''
      }
    },
    methods: {
      actualizar(){
        this.todoMayuscula=this.texto.toUpperCase()
        this.todoMinuscula=this.texto.toLowerCase()
        this.mayusculaMinuscula=this.alternarMayMins(this.texto)
        this.minusculaMayuscula=this.alternarMinsMay(this.texto)
       
       
      },

      alternarMayMins(cadena) {
      let resultado = ''

      for(let i = 0; i < cadena.length; ++i) {
        if (i % 2 == 0) {
            resultado += cadena[i].toUpperCase()
        } else {
            resultado += cadena[i].toLowerCase()
        }
      }

      return resultado;
      },

      alternarMinsMay(cadena) {
      let resultado = ''

      for(let i = 0; i < cadena.length; ++i) {
        if (i % 2 == 0) {
            resultado += cadena[i].toLowerCase()
        } else {
            resultado += cadena[i].toUpperCase()
        }
      }

      return resultado
      },



      
    },
    computed: {
        contar(){
         
         var cant=this.texto.length
         return cant
        }
    }
}


</script>

<style scoped lang="css">
  .src-components-formulario {

  }
</style>
