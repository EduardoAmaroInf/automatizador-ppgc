<template>
    <div>
      <!-- Banner com fundo sólido -->
      <section class="bg-gray-100 text-white py-32 text-center">
        <h1 class="text-6xl font-bold mb-4 text-gray-900">PPGC Ingresso</h1>
        <p class="text-2xl mb-8 text-gray-500">Sistema de Gestão de Candidaturas Para o Programa de Pós-Graduação em Computação</p>
        <div class="space-x-4">
            <UButton
                to="/importar-candidatos"
                class="text-white bg-gray-500 hover:bg-gray-600"
            >
                Importação de candidatos
            </UButton>
            <UButton
                to="/processos-seletivos"
                class="text-gray-500 bg-gray-100 border border-gray-500 hover:bg-gray-200"
            >
                Processos seletivos
            </UButton>
        </div>
      </section>
  
      <!-- Banner de imagem -->
      <section class="w-full">
        <img src="https://via.placeholder.com/1920x400" alt="Banner" class="w-full object-cover" />
      </section>
  
      <!-- Seção de Cards -->
      <section class="p-24 bg-gray-100 dark:bg-gray-900">
        <h2 class="text-3xl font-bold text-gray-800 dark:text-white mb-1 ml-8">Principais processos seletivos</h2>
        <p class="text-xl mb-8 ml-8 text-gray-500">Acesse o processo seletivo desejado</p>
        <div class="space-y-6 px-8">
          <div v-for="(card, index) in cards" :key="index" class="flex flex-col md:flex-row items-center bg-white dark:bg-gray-800 rounded-lg shadow-lg p-6 space-y-4 md:space-y-0 md:space-x-6">
            <img :src="card.image" :alt="card.title" class="w-full md:w-40 h-40 object-cover rounded-lg" />
            <div class="flex-1">
              <h3 class="text-xl font-semibold text-gray-800 dark:text-white mb-2">{{ card.title }}</h3>
              <p class="text-gray-600 dark:text-gray-400 mb-4 max-w-[600px]">{{ card.subtitle }}</p>
              <UButton to="/processo-seletivo" class="bg-gray-500 text-white hover:bg-gray-600 py-2 px-4 rounded-lg">Acessar</UButton>
            </div>
          </div>
        </div>
        <div class="mt-8 text-left px-8">
          <UButton to="/processos-seletivos" class="bg-gray-500 text-white hover:bg-gray-600 py-2 px-4 rounded-lg">Acessar todos os processos seletivos</UButton>
        </div>
      </section>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const cards = ref([
    {
      title: 'Seleção de Estudante Regular (01/2024)',
      subtitle: 'EDITAL Nº 267/2023 SELEÇÃO DE ESTUDANTE REGULAR (01/2024) MESTRADO E DOUTORADO EM CIÊNCIA DA COMPUTAÇÃO INGRESSO 2024/1 E 2024/2',
      image: 'https://via.placeholder.com/400x200',
    },
    {
      title: 'Processo Seletivo 2',
      subtitle: 'EDITAL Nº 031/2023 SELEÇÃO DE ESTUDANTE REGULAR EDITAL SUPLEMENTAR MESTRADO EM CIÊNCIA DA COMPUTAÇÃO INGRESSO 2023/1 E 2023/2',
      image: 'https://via.placeholder.com/400x200',
    },
    {
      title: 'Processo Seletivo 3',
      subtitle: 'EDITAL Nº 183/2021 SELEÇÃO DE ALUNO REGULAR (01/2022) DOUTORADO E MESTRADO EM CIÊNCIA DA COMPUTAÇÃO INGRESSO 2022/1 E 2022/2',
      image: 'https://via.placeholder.com/400x200',
    },
    // Adicione mais cards conforme necessário
  ])
  </script>
  
  <style scoped>
  /* Estilos adicionais, se necessário */
  </style>
  