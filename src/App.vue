<script>
export default {
  data() {
    return {
      valor: null,
      gorjeta: null,
      pessoas: null,
      valor_conta: null,
    };
  },
  methods: {
    calcular_gorjeta() {
      this.valor_conta =
        (this.valor * (1 + Number(this.gorjeta) / 100)) / this.pessoas;
    },
  },
};
</script>

<template>
  <main>
    <h2>Calculadora de gorjeta</h2>
    <div class="container">
      <div class="input_valor">
        <label
          >Qual o valor da conta?
          <input type="number" v-model="valor" name="valor" />
        </label>
      </div>
      <div class="select_gorjeta">
        <label
          >Como foi o serviço?
          <select name="gorjeta" v-model="gorjeta">
            <option value="5">Serviço péssimo - 5% de gorjeta</option>
            <option value="10">Serviço ruim - 10% de gorjeta</option>
            <option value="15">Serviço OK - 15% de gorjeta</option>
            <option value="20">Serviço bom - 20% de gorjeta</option>
            <option value="25">Serviço mais que bom - 25% de gorjeta</option>
            <option value="30">Serviço excepcional - 30% de gorjeta</option>
          </select>
        </label>
      </div>
      <div class="input_pessoas" for="pessoas">
        <label
          >Quantas pessoas estão pagando a conta?
          <input name="pessoas" type="number" v-model="pessoas" />
        </label>
      </div>
      <button @click="calcular_gorjeta">Calcular</button>
      <div class="valor_conta">O valor da conta foi R${{ valor_conta }}</div>
    </div>
  </main>
</template>

<style></style>
