<script setup>
import { ref } from 'vue'


    const novaCidade = ref([''])
    const cidades = ref([
    { nome: 'a', quantidade: 0},
    { nome: 'b', quantidade: 0},
    { nome: 'c', quantidade: 0},
    { nome: 'd', quantidade: 0},
    { nome: 'e', quantidade: 0},
    { nome: 'f', quantidade: 0}])

    function additem (){
    cidades.value.push(novaCidade.value)
    novaCidade.value = ''
  }

  function remover(index) {
    cidades.value.splice(index, 1)
  }

  function addquant (index){
    cidades.value[index].quantidade++
  }

</script>

<template>
    <input type="text" v-model="novaCidade">
    <button @click="additem">adicionar</button>
    <ul>
        <li v-for="(item, index) in cidades" :key="item">{{ item.nome }} - {{ item.quantidade }} <button @click="remover(index)">✘</button>
             <button @click="addquant(index)">+</button></li>
    </ul>
</template>

