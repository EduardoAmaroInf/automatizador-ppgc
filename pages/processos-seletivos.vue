<template>
    <div>
        <!-- Seção Inicial Similar à Home -->
        <section class="bg-gray-100 text-white py-32 text-center">
            <h1 class="text-6xl font-bold mb-4 text-gray-900">Processos Seletivos</h1>
            <p class="text-2xl mb-8 text-gray-500">Encontre e gerencie os processos seletivos vigentes e finalizados</p>
        </section>

        <!-- Filtros Superiores -->
        <section class="p-24 bg-gray-200 dark:bg-gray-900">
            <h2 class="text-3xl font-bold text-gray-800 dark:text-white ">Principais processos seletivos</h2>
            <p class="text-xl mb-8 text-gray-500">Filtre a exibição dos processos seletivos cadastrados</p>
            <div class="flex flex-col md:flex-row md:items-center md:justify-between">
                <!-- Campo de Busca -->
                <div class="mb-4 md:mb-0">
                    <input type="text" placeholder="Buscar processos seletivos..."
                        class="w-full md:w-96 p-3 border border-gray-300 rounded-lg dark:border-gray-700 dark:bg-gray-800 dark:text-white" />
                </div>
                <!-- Filtros de Ordenação -->
                <div class="flex space-x-4">
                    <UButton
                        class="text-gray-500 border border-gray-500 bg-gray-100 hover:bg-gray-200 dark:border-gray-600 dark:text-gray-300 dark:hover:bg-gray-700">
                        Novo
                    </UButton>
                    <UButton
                        class="text-gray-500 border border-gray-500 bg-gray-100 hover:bg-gray-200 dark:border-gray-600 dark:text-gray-300 dark:hover:bg-gray-700">
                        Número de inscritos
                    </UButton>
                    <UButton
                        class="text-gray-500 border border-gray-500 bg-gray-100 hover:bg-gray-200 dark:border-gray-600 dark:text-gray-300 dark:hover:bg-gray-700">
                        Prazo de encerramento
                    </UButton>
                    <UButton
                        class="text-gray-500 border border-gray-500 bg-gray-100 hover:bg-gray-200 dark:border-gray-600 dark:text-gray-300 dark:hover:bg-gray-700">
                        Finalizado
                    </UButton>
                </div>
            </div>
        </section>

        <!-- Listagem de Processos Seletivos -->
        <section class="p-24 bg-gray-100 dark:bg-gray-900 pt-8">
            <div class="flex justify-end space-x-4 mb-8">
                <UButton to="/cadastrar-processo" class="bg-gray-500 text-white hover:bg-gray-600 py-2 px-4 rounded-lg">
                    Cadastrar processo
                </UButton>
            </div>

            <div class="space-y-6">
                <div v-for="(card, index) in cards" :key="index"
                    class="flex flex-col md:flex-row items-center bg-white dark:bg-gray-800 rounded-lg shadow-lg p-6 space-y-4 md:space-y-0 md:space-x-6">
                    <img :src="card.image" :alt="card.title" class="w-full md:w-40 h-40 object-cover rounded-lg" />
                    <div class="flex-1">
                        <h3 class="text-xl font-semibold text-gray-800 dark:text-white mb-2">{{ card.title }}</h3>
                        <p class="text-gray-600 dark:text-gray-400 mb-4 max-w-[600px]">{{ card.subtitle }}</p>
                        <UButton to="/processo-seletivo"
                            class="bg-gray-500 text-white hover:bg-gray-600 py-2 px-4 rounded-lg">Acessar</UButton>
                        <UButton to="/processo-seletivo"
                            class="bg-transparent text-gray-500 border border-gray-500 hover:bg-gray-200 dark:border-gray-600 dark:text-gray-300 dark:hover:bg-gray-700 ml-4">
                            Exportar
                        </UButton>
                    </div>
                </div>
            </div>
        </section>

        <!-- Paginação -->
        <section class="p-8 bg-gray-100 dark:bg-gray-900">
            <div class="flex justify-center space-x-4">
                <UButton
                    class="text-gray-500 border border-gray-500 bg-gray-100 hover:bg-gray-200 dark:border-gray-600 dark:text-gray-300 dark:hover:bg-gray-700">
                    Anterior
                </UButton>
                <UButton
                    class="text-gray-500 border border-gray-500 bg-gray-100 hover:bg-gray-200 dark:border-gray-600 dark:text-gray-300 dark:hover:bg-gray-700">
                    Próximo
                </UButton>
            </div>
        </section>

        <!-- Botões Configurar e Cadastrar -->
        <section class="p-8 bg-gray-100 dark:bg-gray-900">
            <div class="flex justify-end space-x-4">

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
    {
        title: 'Processo Seletivo 4',
        subtitle: 'EDITAL Nº 183/2021 SELEÇÃO DE ALUNO REGULAR (01/2022) DOUTORADO E MESTRADO EM CIÊNCIA DA COMPUTAÇÃO INGRESSO 2022/1 E 2022/2',
        image: 'https://via.placeholder.com/400x200',
    },
    {
        title: 'Processo Seletivo 5',
        subtitle: 'EDITAL Nº 183/2021 SELEÇÃO DE ALUNO REGULAR (01/2022) DOUTORADO E MESTRADO EM CIÊNCIA DA COMPUTAÇÃO INGRESSO 2022/1 E 2022/2',
        image: 'https://via.placeholder.com/400x200',
    },
])
</script>

<style scoped>
/* Estilos adicionais, se necessário */
</style>
