<script setup>
import { reactive } from 'vue';

const estado = reactive({
  numero1: 0,
  numero2: 0,
  filtro: 'adicao',
})


function resultado() {
  const {numero1, numero2, filtro} = estado;

  switch (filtro) {
        case 'adicao':
            return numero1 + numero2;
        case 'subtracao':
            return numero1 - numero2;
        case 'multiplicacao':
            return numero1 * numero2;
        case 'divisao':
            return numero1 / numero2;
        default:
            return 0;
        }
}


</script>

<template>

  <div class="container">
    <h1>CALCULADORA ARITIMÉTICA</h1>

    <input type="number"  @change="evento => estado.numero1 = parseInt(evento.target.value)" @keyup="evento => estado.numero1 = parseInt(evento.target.value)">
  <br/>
    <select @change="evento => estado.filtro = evento.target.value">
      <option value="adicao">+</option>
      <option value="subtracao">-</option>
      <option value="multiplicacao">*</option>
      <option value="divisao">/</option>
    </select>
  
  <br/>
  <input  type="number" @change="evento => estado.numero2 = parseInt(evento.target.value)" @keyup="evento => estado.numero2 = parseInt(evento.target.value)">
  <br/>
  
  <p>Resultado: {{ resultado() }} </p>

  </div>  

</template>

<style scoped>
  .container {
    max-width:300px;
    align-items: center;
    margin: 100px auto;
  }

  h1 {
    text-align: center;
  }

  input {
    margin: 20px auto;
    width: 100%;

  }
  select {
    text-align: center;
    width: 40px;
    margin: 0 130px 0 130px;
  }

  p {
    text-transform: uppercase;
    text-align: center;
    font-weight: bold;
  }
</style>
