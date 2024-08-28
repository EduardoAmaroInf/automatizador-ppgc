<template>
    <!-- Seção Inicial -->
    <section class="bg-gray-100 text-white py-32 text-center">
        <h1 class="text-6xl font-bold mb-4 text-gray-900">Importação de Candidatos</h1>
        <p class="text-2xl mb-8 text-gray-500">Importe candidatos para o processo seletivo</p>
    </section>

    <div class="min-h-screen flex items-center justify-center bg-gray-200 dark:bg-gray-900 py-32">

        <div class="bg-white dark:bg-gray-800 p-8 rounded-lg shadow-lg w-full max-w-lg">
            <!-- Título -->
            <h2 class="text-3xl font-bold text-gray-800 dark:text-white text-center">Configure a importação</h2>
            <p class="text-xl mb-8 text-gray-500 text-center">Selecione o processo seletivo, os arquivos e configurações desejadas</p>

            <!-- Formulário de Importação -->
            <form @submit.prevent="handleImport">
                <!-- Campo de Seleção de Processo Seletivo -->
                <div class="mb-4">
                    <label for="process" class="block text-gray-700 dark:text-gray-300 mb-2">Processo Seletivo</label>
                    <select v-model="process" id="process"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required>
                        <option value="">Selecione um processo seletivo</option>
                        <option value="process1">Processo Seletivo 1</option>
                        <option value="process2">Processo Seletivo 2</option>
                        <option value="process3">Processo Seletivo 3</option>
                    </select>
                </div>

                <!-- Campo de Seleção de Configuração -->
                <div class="mb-4">
                    <label for="config" class="block text-gray-700 dark:text-gray-300 mb-2">Configuração</label>
                    <select v-model="config" id="config"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required>
                        <option value="">Selecione uma configuração</option>
                        <option value="config1">Configuração 1</option>
                        <option value="config2">Configuração 2</option>
                        <option value="config3">Configuração 3</option>
                    </select>
                </div>

                <!-- Campo de Upload de Arquivo CSV -->
                <div class="mb-4">
                    <label for="file" class="block text-gray-700 dark:text-gray-300 mb-2">Arquivo CSV</label>
                    <input type="file" id="file" accept=".csv"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        @change="handleFileChange" required />
                </div>

                <!-- Checkbox para Substituir Candidatos -->
                <div class="mb-4 flex items-start">
                    <input v-model="replaceCandidates" type="checkbox" id="replaceCandidates"
                        class="form-checkbox h-5 w-5 text-gray-600 dark:text-gray-400" />
                    <label for="replaceCandidates" class="ml-2 text-gray-700 dark:text-gray-300">
                        Substituir candidatos existentes
                        <p class="text-sm text-gray-500 dark:text-gray-400">Ao selecionar esta opção, os candidatos
                            importados irão substituir os já cadastrados.</p>
                    </label>
                </div>

                <!-- Checkbox para Doutorado -->
                <div class="mb-4 flex items-center">
                    <input v-model="isDoctorate" type="checkbox" id="doctorate"
                        class="form-checkbox h-5 w-5 text-gray-600 dark:text-gray-400" />
                    <label for="doctorate" class="ml-2 text-gray-700 dark:text-gray-300">Doutorado</label>
                </div>

                <!-- Checkbox para Mestrado -->
                <div class="mb-4 flex items-center">
                    <input v-model="isMaster" type="checkbox" id="master"
                        class="form-checkbox h-5 w-5 text-gray-600 dark:text-gray-400" />
                    <label for="master" class="ml-2 text-gray-700 dark:text-gray-300">Mestrado</label>
                </div>

                <!-- Botão Importar -->
                <div class="flex items-center justify-center">
                    <UButton type="submit" class="w-full text-white bg-gray-500 hover:bg-gray-600 py-2 px-4 rounded-lg">
                        Importar
                    </UButton>
                </div>
            </form>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const process = ref('')
const config = ref('')
const file = ref(null)
const replaceCandidates = ref(false)
const isDoctorate = ref(false)
const isMaster = ref(false)

const handleFileChange = (event) => {
    file.value = event.target.files[0]
}

const handleImport = () => {
    // Aqui você pode adicionar a lógica de importação, como chamar uma API
    console.log('Processo Seletivo:', process.value)
    console.log('Configuração:', config.value)
    console.log('Arquivo:', file.value)
    console.log('Substituir Candidatos:', replaceCandidates.value)
    console.log('Doutorado:', isDoctorate.value)
    console.log('Mestrado:', isMaster.value)
    // Redirecionar ou mostrar mensagens de erro/sucesso conforme necessário
}
</script>

<style scoped>
/* Estilos adicionais, se necessário */
</style>
