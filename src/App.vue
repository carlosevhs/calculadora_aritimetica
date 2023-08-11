<script>

export default {
    data() {
    return {
        numero1: 0,
        numero2: 0,
        operacao: 'soma'
    };
    },
    computed: {
    resultado() {
        const num1 = parseFloat(this.numero1);
        const num2 = parseFloat(this.numero2);

        switch (this.operacao) {
        case 'soma':
            return num1 + num2;
        case 'subtracao':
            return num1 - num2;
        case 'multiplicacao':
            return num1 * num2;
        case 'divisao':
            return num1 / num2;
        default:
            return 0;
        }
    }
    },
    methods: {
    atualizarCalculo() {
        
    }
    }
};

</script>

<template>

  <div class="container">
    <input type="number" v-model="numero1" @input="atualizarCalculo" />
    <br/>
    <select class="select" v-model="operacao" @change="atualizarCalculo">
        <option value="soma">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
        <option value="divisao">/</option>
    </select>
    <br/>
    <input type="number" v-model="numero2" @input="atualizarCalculo" />
    <p>Resultado: {{ resultado }}</p>
  </div>
    
    
</template>

<style >

  .container {
    max-width:300px;
    align-items: center;
    margin: 100px auto;
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