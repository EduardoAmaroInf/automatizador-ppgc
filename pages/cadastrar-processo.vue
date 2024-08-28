<template>
    <!-- Seção Inicial Similar à Home -->
    <section class="bg-gray-100 text-white py-32 text-center">
        <h1 class="text-6xl font-bold mb-4 text-gray-900">Cadastro de processo seletivo</h1>
        <p class="text-2xl mb-8 text-gray-500">Cadastre um novo processo seletivo</p>
    </section>

    <div class="min-h-screen flex items-center justify-center bg-gray-200 dark:bg-gray-900 py-32">

        <div class="bg-white dark:bg-gray-800 p-8 rounded-lg shadow-lg w-full max-w-lg">
            <!-- Título -->
            <h2 class="text-3xl font-bold text-gray-800 dark:text-white text-center">Cadastro de Processo Seletivo
            </h2>
            <p class="text-xl mb-8 text-gray-500 text-center">Adicione os dados do processo seletivo</p>

            <!-- Formulário de Cadastro -->
            <form @submit.prevent="handleSignup">
                <!-- Campo de Nome -->
                <div class="mb-4">
                    <label for="name" class="block text-gray-700 dark:text-gray-300 mb-2">Nome</label>
                    <input v-model="name" type="text" id="name"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required />
                </div>

                <!-- Campo de Semestre de Ingresso -->
                <div class="mb-4">
                    <label for="semester" class="block text-gray-700 dark:text-gray-300 mb-2">Semestre de
                        Ingresso</label>
                    <input v-model="semester" type="text" id="semester"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required />
                </div>

                <!-- Campo de Data de Início -->
                <div class="mb-4">
                    <label for="startDate" class="block text-gray-700 dark:text-gray-300 mb-2">Data de Início</label>
                    <input v-model="startDate" type="date" id="startDate"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required />
                </div>

                <!-- Campo de Data de Término -->
                <div class="mb-4">
                    <label for="endDate" class="block text-gray-700 dark:text-gray-300 mb-2">Data de Término</label>
                    <input v-model="endDate" type="date" id="endDate"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required />
                </div>

                <!-- Campo de Link para Edital -->
                <div class="mb-4">
                    <label for="link" class="block text-gray-700 dark:text-gray-300 mb-2">Link para Edital</label>
                    <input v-model="link" type="url" id="link"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required />
                </div>

                <!-- Configuração -->
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

                <!-- Checkbox Doutorado -->
                <div class="mb-4 flex items-center">
                    <input v-model="isDoctorate" type="checkbox" id="doctorate"
                        class="form-checkbox h-5 w-5 text-gray-600 dark:text-gray-400" />
                    <label for="doctorate" class="ml-2 text-gray-700 dark:text-gray-300">Doutorado</label>
                </div>

                <!-- Checkbox Mestrado -->
                <div class="mb-4 flex items-center">
                    <input v-model="isMaster" type="checkbox" id="master"
                        class="form-checkbox h-5 w-5 text-gray-600 dark:text-gray-400" />
                    <label for="master" class="ml-2 text-gray-700 dark:text-gray-300">Mestrado</label>
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

const name = ref('')
const semester = ref('')
const startDate = ref('')
const endDate = ref('')
const link = ref('')
const config = ref('')
const isDoctorate = ref(false)
const isMaster = ref(false)

const handleSignup = () => {
    // Aqui você pode adicionar a lógica de cadastro, como chamar uma API
    console.log('Nome:', name.value)
    console.log('Semestre de Ingresso:', semester.value)
    console.log('Data de Início:', startDate.value)
    console.log('Data de Término:', endDate.value)
    console.log('Link para Edital:', link.value)
    console.log('Configuração:', config.value)
    console.log('Doutorado:', isDoctorate.value)
    console.log('Mestrado:', isMaster.value)
    // Redirecionar ou mostrar mensagens de erro/sucesso conforme necessário
}
</script>

<style scoped>
/* Estilos adicionais, se necessário */
</style>
