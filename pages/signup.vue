<template>
    <div class="min-h-screen flex items-center justify-center bg-gray-100 dark:bg-gray-900">
        <div class="bg-white dark:bg-gray-800 p-8 rounded-lg shadow-lg w-full max-w-md">
            <!-- Título -->
            <h2 class="text-2xl font-bold text-gray-800 dark:text-white text-center mb-6">Cadastro</h2>

            <!-- Formulário de Cadastro -->
            <form @submit.prevent="handleSignup">
                <!-- Campo de Nome -->
                <div class="mb-4">
                    <label for="name" class="block text-gray-700 dark:text-gray-300 mb-2">Nome</label>
                    <input
                        v-model="name"
                        type="text"
                        id="name"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required
                    />
                </div>

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
                <div class="mb-4">
                    <label for="password" class="block text-gray-700 dark:text-gray-300 mb-2">Senha</label>
                    <input
                        v-model="password"
                        type="password"
                        id="password"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required
                    />
                </div>

                <!-- Campo de Confirmação de Senha -->
                <div class="mb-6">
                    <label for="confirmPassword" class="block text-gray-700 dark:text-gray-300 mb-2">Confirmar Senha</label>
                    <input
                        v-model="confirmPassword"
                        type="password"
                        id="confirmPassword"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        required
                    />
                </div>

                <!-- Botão de Cadastro -->
                <div class="flex items-center justify-between">
                    <UButton
                        type="submit"
                        class="w-full text-white bg-gray-500 hover:bg-gray-600 py-2 px-4 rounded-lg"
                    >
                        Cadastrar
                    </UButton>
                </div>
            </form>

            <!-- Link para Login -->
            <p class="text-center text-gray-600 dark:text-gray-400 mt-6">
                Já tem uma conta?
                <ULink to="/login" class="text-gray-500 hover:underline">Faça login</ULink>
            </p>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const password = ref('')
const confirmPassword = ref('')

const handleSignup = () => {
    // Aqui você pode adicionar a lógica de cadastro, como chamar uma API
    if (password.value !== confirmPassword.value) {
        alert('As senhas não coincidem.')
        return
    }
    console.log('Nome:', name.value)
    console.log('Email:', email.value)
    console.log('Password:', password.value)
    // Redirecionar ou mostrar mensagens de erro/sucesso conforme necessário
}
</script>

<style scoped>
/* Estilos adicionais, se necessário */
</style>
