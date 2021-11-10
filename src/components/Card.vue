<template>
  <div class="card">
    <input type="text" placeholder="CEP" disabled :value="dados.cep" />
    <input type="text" placeholder="UF" disabled :value="dados.uf" />
    <input
      type="text"
      placeholder="Cidade"
      disabled
      :value="dados.localidade"
    />
    <input
      type="text"
      placeholder="Logradouro"
      disabled
      :value="dados.logradouro"
    />
    <input type="text" placeholder="Bairro" disabled :value="dados.bairro" />
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    dados: {
      type: Object,
      required: false,
    },
  },
}
</script>

<style>
.card {
  max-width: 500px;
  width: 90%;
  margin: 0 auto;
  background-color: #fff;
  display: flex;
  flex-direction: column;
  gap: 15px;
  padding: 20px;
  border-left: 10px solid lightcoral;
}

.card input {
  width: 100%;
  height: 40px;
  padding: 10px;
}

.card__logradouro {
  display: flex;
  align-items: center;
  gap: 5px;
}

@media screen and (min-width: 768px) {
  .card input {
    width: 60%;
    margin: 0 auto;
  }
}
</style>
