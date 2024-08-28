<template>
    <footer class="bg-white border-t-2 dark:bg-gray-800 py-32 px-8">
        <div class="flex flex-col md:flex-row md:justify-between">
            <!-- Logo e Redes Sociais -->
            <div class="mb-8 md:mb-0 flex flex-col items-center">
                <img src="https://via.placeholder.com/200x200" alt="Logo Placeholder" class="w-10 h-10" />
                <h1 class="text-xl font-bold text-gray-600 mb-4">PPGC Ingresso</h1>
                <div class="flex space-x-4">
                    <UIcon v-for="icon in socialIcons" :key="icon.name" :name="icon.name" :class="icon.class"
                        class="w-6 h-6 hover:cursor-pointer" />
                </div>
            </div>

            <!-- Links das Colunas -->
            <div class="flex flex-col md:flex-row space-y-8 md:space-y-0 md:space-x-16">
                <div v-for="(column, index) in menuColumns" :key="index">
                    <h3 class="text-lg font-semibold text-gray-800 dark:text-white mb-4">{{ column.title }}</h3>
                    <ul class="space-y-2">
                        <li v-for="link in column.links" :key="link.path">
                            <ULink :to="link.path"
                                class="text-gray-600 dark:text-gray-400 hover:text-gray-800 dark:hover:text-white">
                                {{ link.label }}
                            </ULink>
                        </li>
                    </ul>
                </div>
            </div>
            <div></div>
        </div>
    </footer>
</template>

<script setup>
import { ref } from 'vue'

// Definindo os ícones das redes sociais
const socialIcons = ref([
    { name: 'i-ph:facebook-logo', class: 'text-blue-600 hover:text-blue-800' },
    { name: 'i-ph:twitter-logo', class: 'text-blue-400 hover:text-blue-600' },
    { name: 'i-ph:instagram-logo', class: 'text-pink-500 hover:text-pink-700' },
    { name: 'i-ph:linkedin-logo', class: 'text-blue-700 hover:text-blue-900' },
])

// Definindo as colunas do menu e seus links
const menuColumns = ref([
    {
        title: 'PPGC',
        links: [
            { label: 'Editais de ingresso', path: '/home' },
            { label: 'Sobre o PPGC', path: '/home' },
            { label: 'FAQ - Alunos', path: '/home' },
        ],
    },
    {
        title: 'PPGC Ingresso',
        links: [
            { label: 'Importar', path: '/home' },
            { label: 'Processos seletivos', path: '/home' },
            { label: 'Configurações', path: '/home' },
        ],
    },
    {
        title: 'Sobre',
        links: [
            { label: 'Sobre o sistema', path: '/home' },
            { label: 'FAQ', path: '/home' },
            { label: 'Fale conosco', path: '/home' },
        ],
    },
])
</script>

<style scoped>
/* Adicione estilos adicionais, se necessário */
</style>
