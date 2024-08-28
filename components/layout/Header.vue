<template>
    <div class="flex items-center justify-between h-24 px-8 border-b-2 bg-white dark:bg-gray-800">
        <!-- Logo -->
        <div class="flex items-center">
            <img 
                src="https://via.placeholder.com/200x200" 
                alt="Logo Placeholder" 
                class="w-10 h-10 mr-4"
            />
            <h1 class="text-xl font-bold text-gray-600">PPGC Ingresso</h1>
        </div>
        
        <!-- Menu Links -->
        <nav class="flex space-x-6">
            <ULink
                v-for="link in menuLinks"
                :key="link.path"
                :to="link.path"
                active-class="text-gray-700"
                inactive-class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200"
            >
                {{ link.label }}
            </ULink>
        </nav>

        <!-- Botões de Login e Cadastro -->
        <div class="flex space-x-4">
            <UButton
                to="/login"
                class="text-white bg-gray-500 hover:bg-gray-600"
            >
                Login
            </UButton>
            <UButton
                to="/signup"
                class="bg-gray-100 text-gray-500 border border-gray-500 hover:bg-gray-200"
            >
                Cadastro
            </UButton>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

// Definindo os links do menu como uma constante
const menuLinks = ref([
    { label: 'Home', path: '/home' },
    { label: 'Importar', path: '/importar-candidatos' },
    { label: 'Processos seletivos', path: '/processos-seletivos' },
    { label: 'Configurações', path: '/cadastrar-configuracao' },
])
</script>
