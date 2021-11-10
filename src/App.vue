<template>
  <div id="app">
    <div class="search">
      <input
        type="text"
        placeholder="Digite um CEP..."
        v-model="cep"
        maxlength="8"
      />
      <button @click="getCep">Pesquisar</button>
    </div>
    <Card :dados="dados" />
  </div>
</template>

<script>
import Card from './components/Card'

export default {
  name: 'App',
  components: {
    Card,
  },
  data: () => ({
    cep: '',
    dados: {},
  }),
  methods: {
    getCep() {
      fetch(`https://viacep.com.br/ws/${this.cep}/json/`)
        .then((res) => res.json())
        .then((data) => (this.dados = data))
      this.cep = ''
    },
  },
}
</script>

<style scoped>
#app {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 60px;
  background-color: lightblue;
}

.search input {
  border: none;
  height: 40px;
  outline: none;
  padding: 5px 10px;
  font-size: 16px;
}

.search button {
  background-color: lightcoral;
  height: 40px;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
  border-top-right-radius: 8px;
  border-bottom-right-radius: 8px;
  font-size: 16px;
  font-weight: 600;
  color: #fff;
}
</style>
