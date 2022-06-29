<template>

  <section class="src-components-formulario">
    <h1>Recuperatorio</h1>
    <label for="texto">Texto a convertir </label>   
     <input type="text" v-model="texto" @input="actualizar()"> <br>
    <hr>
    <p>{{ todoMayuscula }}  (TODO MAYUSCULA) </p>
    <p>{{ todoMinuscula }}  (TODO MINUSCULA)</p>
    <p>{{ codificado }}  (CODIFICADO)</p>
    <p>{{ mayusculaMinuscula }}  (MAYUSCULA-MINUSCULA)</p>
    <p>{{ minusculaMayuscula }}  (MINUSCULA-MAYUSCULA)</p>
    <p>cantidad: {{contar}} </p>

    <hr>
    <br>
    <h2>Respuestas:</h2>
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
        codificado:'',
      }
    },
    methods: {
      actualizar(){
        this.todoMayuscula=this.texto.toUpperCase()
        this.todoMinuscula=this.texto.toLowerCase()
        this.mayusculaMinuscula=this.alternarMayMins(this.texto)
        this.minusculaMayuscula=this.alternarMinsMay(this.texto)
        this.codificado=this.codificar(this.texto)
       
       
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

      for(let i = 0; i < cadena.length; i++) {
        if (i % 2 == 0) {
            resultado += cadena[i].toLowerCase()
        } else {
            resultado += cadena[i].toUpperCase()
        }
      }

      return resultado
      },

      codificar(cadenaAconvertir){
        let convertida=''
        let cadena=cadenaAconvertir.toLowerCase()
        for(let i=0;i <cadena.length;i++){
          if(cadena[i]=='a'){
            convertida+='u'
          }else if(cadena[i]=='e'){
          convertida+='o'
         }else if(cadena[i]=='o'){
          convertida+='e'
         }else if(cadena[i]=='u'){
          convertida+='a'
         }else{
          convertida+=cadena[i]
         }


      }
      return convertida
      }
      
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
