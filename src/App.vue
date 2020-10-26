<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <h1>{{titu}}</h1>

    <li v-for="tarefa in tarefas" :key="tarefa.id">
      <input type="checkbox" v-model="tarefa.estaCompleta">
      <h4>{{ tarefa.descricao | allCapital() }}</h4>
    </li>

    <p>Tarefas feitas:</p>
    <li v-for="tarefa in tarefas" :key="tarefa.id">
      <h4 v-if="tarefa.estaCompleta == true">{{tarefa.descricao}}</h4>
    </li>

    
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  data(){
    return {
      titu: "Tarefas:",
      tarefas: [
        { id: 1, descricao: "Lavar louça.", estaCompleta: false },
        { id: 2, descricao: "Colocar roupas para lavar.", estaCompleta: false },
        { id: 3, descricao: "Limpar terraço.", estaCompleta: false }
      ]
    }
  }, filters: {
    allCapital(str){
      return str.toUpperCase()
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

li{
  display: flex;
  text-decoration: none;
  place-items: center;
}

</style>
