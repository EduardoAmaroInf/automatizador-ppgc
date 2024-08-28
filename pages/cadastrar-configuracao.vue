<template>
    <!-- Seção Inicial Similar às Outras -->
    <section class="bg-gray-100 text-white py-32 text-center">
        <h1 class="text-6xl font-bold mb-4 text-gray-900">Cadastro de Configuração</h1>
        <p class="text-2xl mb-8 text-gray-500">Defina as configurações para o processo seletivo</p>
    </section>

    <div class="min-h-screen flex items-center justify-center bg-gray-200 dark:bg-gray-900 py-32">

        <div class="bg-white dark:bg-gray-800 p-8 rounded-lg shadow-lg w-full max-w-lg">
            <!-- Título -->
            <h2 class="text-3xl font-bold text-gray-800 dark:text-white text-center">Cadastro de Configuração</h2>
            <p class="text-xl mb-8 text-gray-500 text-center">Defina os pesos das notas e opções de cota</p>

            <!-- Formulário de Cadastro -->
            <form @submit.prevent="handleConfigSubmit">
                <!-- Campo de Peso da Nota Acadêmica -->
                <div class="mb-4">
                    <label for="academicWeight" class="block text-gray-700 dark:text-gray-300 mb-2">Peso da Nota
                        Acadêmica</label>
                    <input v-model="academicWeight" type="number" id="academicWeight" step="0.1" min="0" max="1"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required />
                </div>

                <!-- Campo de Peso da Nota das Publicações -->
                <div class="mb-4">
                    <label for="publicationsWeight" class="block text-gray-700 dark:text-gray-300 mb-2">Peso da Nota das
                        Publicações</label>
                    <input v-model="publicationsWeight" type="number" id="publicationsWeight" step="0.1" min="0" max="1"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required />
                </div>

                <!-- Campo de Peso da Nota do Projeto -->
                <div class="mb-4">
                    <label for="projectWeight" class="block text-gray-700 dark:text-gray-300 mb-2">Peso da Nota do
                        Projeto</label>
                    <input v-model="projectWeight" type="number" id="projectWeight" step="0.1" min="0" max="1"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required />
                </div>

                <!-- Campo de Peso da Nota da Entrevista -->
                <div class="mb-4">
                    <label for="interviewWeight" class="block text-gray-700 dark:text-gray-300 mb-2">Peso da Nota da
                        Entrevista</label>
                    <input v-model="interviewWeight" type="number" id="interviewWeight" step="0.1" min="0" max="1"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required />
                </div>

                <!-- Checkbox de Cota -->
                <div class="mb-4 flex items-center">
                    <input v-model="hasQuota" type="checkbox" id="quota"
                        class="form-checkbox h-5 w-5 text-gray-600 dark:text-gray-400" />
                    <label for="quota" class="ml-2 text-gray-700 dark:text-gray-300">Aplicar Cota</label>
                </div>

                <!-- Botão Cadastrar -->
                <div class="flex items-center justify-center">
                    <UButton type="submit" class="w-full text-white bg-gray-500 hover:bg-gray-600 py-2 px-4 rounded-lg">
                        Cadastrar
                    </UButton>
                </div>
            </form>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const academicWeight = ref(0)
const publicationsWeight = ref(0)
const projectWeight = ref(0)
const interviewWeight = ref(0)
const hasQuota = ref(false)

const handleConfigSubmit = () => {
    // Lógica para processar e salvar a configuração
    console.log('Peso da Nota Acadêmica:', academicWeight.value)
    console.log('Peso da Nota das Publicações:', publicationsWeight.value)
    console.log('Peso da Nota do Projeto:', projectWeight.value)
    console.log('Peso da Nota da Entrevista:', interviewWeight.value)
    console.log('Aplicar Cota:', hasQuota.value)
    // Redirecionar ou mostrar mensagens de erro/sucesso conforme necessário
}
</script>

<style scoped>
/* Estilos adicionais, se necessário */
</style>
