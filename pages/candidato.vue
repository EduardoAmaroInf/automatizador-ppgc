<template>
    <!-- Seção Inicial Similar às Outras -->
    <section class="bg-gray-100 text-white py-32 text-center">
        <h1 class="text-6xl font-bold mb-4 text-gray-900">Dados do Candidato</h1>
        <p class="text-2xl mb-8 text-gray-500">Visualize e edite seus dados cadastrados</p>
    </section>

    <!-- Slider para Seleção de Processo Seletivo -->
    <div class="bg-gray-200 dark:bg-gray-900 py-8 px-4">
        <label for="processoSeletivo" class="block text-gray-700 dark:text-gray-300 mb-2 text-center">Selecione o
            Processo Seletivo</label>
        <select v-model="selectedProcessoSeletivo" id="processoSeletivo"
            class="block mx-auto w-full max-w-md px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500">
            <option v-for="processo in processosSeletivos" :key="processo.id" :value="processo.id">
                {{ processo.nome }}
            </option>
        </select>
    </div>

    <!-- Formulário de Edição -->
    <div class="min-h-screen flex items-center justify-center bg-gray-200 dark:bg-gray-900 pt-8 pb-32">
        <div class="bg-white dark:bg-gray-800 p-8 rounded-lg shadow-lg w-full max-w-lg">
            <h2 class="text-3xl font-bold text-gray-800 dark:text-white text-center mb-6">Dados do Candidato</h2>

            <!-- Imagem do Candidato -->
            <div class="flex justify-center mb-6">
                <img :src="candidateImage" alt="Foto do Candidato" class="w-32 h-32 object-cover rounded-full" />
            </div>

            <form @submit.prevent="handleUpdate">
                <!-- Campos de Dados -->
                <div class="mb-4" v-for="(field, index) in candidateFields" :key="index">
                    <label :for="field.id" class="block text-gray-700 dark:text-gray-300 mb-2">{{ field.label }}</label>
                    <input :v-model="field.model" :type="field.type" :id="field.id"
                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500"
                        :disabled="!isEditing" required />
                </div>
                <div>
                    <ULink class="text-gray-500 hover:underline mb-4">Ver mais</ULink>
                </div>

                <!-- Botão de Editar -->
                <div class="flex justify-center mb-4">
                    <UButton type="button" @click="isEditing = !isEditing"
                        class="w-full text-white bg-gray-500 hover:bg-gray-600 py-2 px-4 rounded-lg">
                        {{ isEditing ? 'Salvar' : 'Editar' }}
                    </UButton>
                </div>
            </form>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

// Dados mockados para os processos seletivos
const processosSeletivos = ref([
    { id: 1, nome: 'Seleção de Estudante Regular (01/2024)' },
    { id: 2, nome: 'Seleção de Estudante Regular (02/2024)' },
])

// Estado do formulário
const selectedProcessoSeletivo = ref(processosSeletivos.value[0].id)
const isEditing = ref(false)

// Imagem do candidato
const candidateImage = ref('https://via.placeholder.com/150') // Substitua pelo link da imagem real

// Campos de dados do candidato
const candidateFields = ref([
    { id: 'name', label: 'Nome', model: ref('João Silva'), type: 'text' },
    { id: 'email', label: 'Email', model: ref('joao.silva@example.com'), type: 'email' },
    { id: 'cpf', label: 'CPF', model: ref('123.456.789-00'), type: 'text' },
    { id: 'phone', label: 'Telefone', model: ref('(11) 98765-4321'), type: 'text' },
    { id: 'address', label: 'Endereço', model: ref('Rua Exemplo, 123, Bairro, Cidade, Estado'), type: 'text' },
    { id: 'course', label: 'Curso', model: ref('Mestrado em Ciência da Computação'), type: 'text' },
])

const handleUpdate = () => {
    // Lógica de atualização dos dados
    if (isEditing.value) {
        console.log('Dados atualizados:', candidateFields.value.map(field => ({ [field.label]: field.model.value })))
    }
    isEditing.value = false
}
</script>

<style scoped>
/* Estilos adicionais, se necessário */
</style>
