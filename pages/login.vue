<template>
    <div class="min-h-screen flex items-center justify-center bg-gray-100 dark:bg-gray-900">
        <div class="bg-white dark:bg-gray-800 p-8 rounded-lg shadow-lg w-full max-w-md">
            <!-- Título -->
            <h2 class="text-2xl font-bold text-gray-800 dark:text-white text-center mb-6">Login</h2>

            <!-- Formulário de Login -->
            <form @submit.prevent="handleLogin">
                <!-- Campo de Email -->
                <div class="mb-4">
                    <label for="email" class="block text-gray-700 dark:text-gray-300 mb-2">Email</label>
                    <input
                        v-model="email"
                        type="email"
                        id="email"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required
                    />
                </div>

                <!-- Campo de Senha -->
                <div class="mb-6">
                    <label for="password" class="block text-gray-700 dark:text-gray-300 mb-2">Senha</label>
                    <input
                        v-model="password"
                        type="password"
                        id="password"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required
                    />
                </div>

                <!-- Botão de Login -->
                <div class="flex items-center justify-between">
                    <UButton
                        type="submit"
                        class="w-full text-white bg-gray-500 hover:bg-gray-600 py-2 px-4 rounded-lg"
                    >
                        Entrar
                    </UButton>
                </div>
            </form>

            <!-- Link para Cadastro -->
            <p class="text-center text-gray-600 dark:text-gray-400 mt-6">
                Não tem uma conta?
                <ULink to="/signup" class="text-gray-500 hover:underline">Cadastre-se</ULink>
            </p>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const email = ref('')
const password = ref('')

const handleLogin = () => {
    // Aqui você pode adicionar a lógica de autenticação, como chamar uma API
    console.log('Email:', email.value)
    console.log('Password:', password.value)
    // Redirecionar ou mostrar mensagens de erro/sucesso conforme necessário
}
</script>

<style scoped>
/* Estilos adicionais, se necessário */
</style>
