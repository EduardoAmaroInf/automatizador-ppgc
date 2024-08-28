<template>
    <div>
        <!-- Seção Inicial -->
        <section class="bg-gray-100 text-center py-32">
            <h1 class="text-6xl font-bold text-gray-900 mb-4">Seleção de Estudante Regular (01/2024)</h1>
            <p class="text-2xl text-gray-500 mb-8">EDITAL Nº 267/2023</p>
            <p class="text-xl text-gray-500 mb-4">
                SELEÇÃO DE ESTUDANTE REGULAR (01/2024) <br />
                MESTRADO E DOUTORADO EM CIÊNCIA DA COMPUTAÇÃO <br />
                INGRESSO 2024/1 E 2024/2
            </p>
            <div class="flex justify-center">
                <UButton @click="isEditable = !isEditable"
                    class="text-white bg-gray-500 hover:bg-gray-600 py-2 px-4 rounded-lg">
                    Editar
                </UButton>
                <UButton
                    class="bg-transparent text-gray-500 border border-gray-500 hover:bg-gray-200 dark:border-gray-600 dark:text-gray-300 dark:hover:bg-gray-700 ml-4">
                    Exportar
                </UButton>
            </div>
        </section>

        <!-- Seção de Cadastro -->
        <section class="bg-gray-200 dark:bg-gray-900 py-32">
            <h2 class="text-3xl font-bold text-center text-gray-800 dark:text-white mb-6">Dados do processo seletivo
            </h2>
            <div class="bg-white dark:bg-gray-800 p-6 rounded-lg shadow-lg max-w-3xl mx-auto">
                <form>
                    <div class="mb-4">
                        <label for="name" class="block text-gray-700 dark:text-gray-300 mb-2">Nome</label>
                        <input v-model="formData.name" :disabled="!isEditable" type="text" id="name"
                            class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500" />
                    </div>
                    <div class="mb-4">
                        <label for="semester" class="block text-gray-700 dark:text-gray-300 mb-2">Semestre de
                            Ingresso</label>
                        <input v-model="formData.semester" :disabled="!isEditable" type="text" id="semester"
                            class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500" />
                    </div>
                    <div class="mb-4">
                        <label for="start-date" class="block text-gray-700 dark:text-gray-300 mb-2">Data de
                            Início</label>
                        <input v-model="formData.startDate" :disabled="!isEditable" type="date" id="start-date"
                            class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500" />
                    </div>
                    <div class="mb-4">
                        <label for="end-date" class="block text-gray-700 dark:text-gray-300 mb-2">Data de
                            Término</label>
                        <input v-model="formData.endDate" :disabled="!isEditable" type="date" id="end-date"
                            class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500" />
                    </div>
                    <div class="mb-4">
                        <label for="link" class="block text-gray-700 dark:text-gray-300 mb-2">Link para Edital</label>
                        <input v-model="formData.link" :disabled="!isEditable" type="url" id="link"
                            class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500" />
                    </div>
                    <div class="mb-4">
                        <label for="config" class="block text-gray-700 dark:text-gray-300 mb-2">Configuração</label>
                        <select v-model="formData.config" :disabled="!isEditable" id="config"
                            class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white focus:outline-none focus:border-gray-500">
                            <option value="doutorado">Doutorado</option>
                            <option value="mestrado">Mestrado</option>
                        </select>
                    </div>
                    <div class="flex items-center mb-4">
                        <input v-model="formData.doutorado" :disabled="!isEditable" type="checkbox" id="doutorado"
                            class="mr-2" />
                        <label for="doutorado" class="text-gray-700 dark:text-gray-300">Doutorado</label>
                    </div>
                    <div class="flex items-center mb-4">
                        <input v-model="formData.mestrado" :disabled="!isEditable" type="checkbox" id="mestrado"
                            class="mr-2" />
                        <label for="mestrado" class="text-gray-700 dark:text-gray-300">Mestrado</label>
                    </div>
                    <div class="text-center">
                        <UButton v-if="isEditable" @click="handleSave"
                            class="bg-gray-500 text-white hover:bg-gray-600 py-2 px-4 rounded-lg">
                            Salvar
                        </UButton>
                    </div>
                    <div class="flex justify-center mb-4">
                        <UButton
                            class="w-full text-white bg-gray-500 hover:bg-gray-600 py-2 px-4 rounded-lg">
                            Editar
                        </UButton>
                    </div>
                </form>
            </div>
        </section>

        <!-- Listagem de Candidatos -->
        <section class="p-24 bg-gray-100 dark:bg-gray-900">
            <h2 class="text-3xl font-bold text-gray-800 dark:text-white ">Candidatos</h2>
            <p class="text-xl mb-8 text-gray-500">Candidatos já adicionados ao processo seletivo</p>
            <div class="flex justify-end space-x-4 mb-8">
                <UButton to="/importar-candidatos" class="bg-gray-500 text-white hover:bg-gray-600 py-2 px-4 rounded-lg">
                    Importar
                </UButton>
                <UButton to="" class="bg-gray-500 text-white hover:bg-gray-600 py-2 px-4 rounded-lg">
                    Adicionar candidato
                </UButton>
                <UButton class="bg-gray-500 text-white hover:bg-gray-600 py-2 px-4 rounded-lg">
                    Gerar classificação
                </UButton>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
                <div v-for="(candidate, index) in candidates" :key="index"
                    class="bg-white dark:bg-gray-800 rounded-lg shadow-lg p-6 flex flex-col items-center">
                    <img :src="candidate.image" :alt="candidate.name"
                        class="w-32 h-32 object-cover rounded-full mb-4" />
                    <h3 class="text-xl font-semibold text-gray-800 dark:text-white mb-2">{{ candidate.name }}</h3>
                    <p class="text-gray-600 dark:text-gray-400 mb-4">{{ candidate.description }}</p>
                    <UButton to="/candidato" class="bg-gray-500 text-white hover:bg-gray-600 py-2 px-4 rounded-lg">
                        Acessar Candidato
                    </UButton>
                </div>
            </div>
        </section>

        <!-- Paginação -->
        <section class="p-8 bg-gray-100 dark:bg-gray-900 pb-32">
            <div class="flex justify-center space-x-4">
                <UButton
                    class="bg-transparent text-gray-500 border border-gray-500 hover:bg-gray-200 dark:border-gray-600 dark:text-gray-300 dark:hover:bg-gray-700">
                    Anterior
                </UButton>
                <UButton
                    class="bg-transparent text-gray-500 border border-gray-500 hover:bg-gray-200 dark:border-gray-600 dark:text-gray-300 dark:hover:bg-gray-700">
                    Próximo
                </UButton>
            </div>
        </section>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const isEditable = ref(false);

const formData = ref({
    name: 'Seleção de Estudante Regular (01/2024)',
    semester: '2024/1 e 2024/2',
    startDate: '2024-01-01',
    endDate: '2024-06-30',
    link: 'https://exemplo.com/edital',
    config: 'mestrado',
    doutorado: true,
    mestrado: true,
});

const candidates = ref([
    {
        name: 'Candidato 1',
        description: 'Descrição do Candidato 1',
        image: 'https://via.placeholder.com/400x200',
    },
    {
        name: 'Candidato 2',
        description: 'Descrição do Candidato 2',
        image: 'https://via.placeholder.com/400x200',
    },
    {
        name: 'Candidato 2',
        description: 'Descrição do Candidato 2',
        image: 'https://via.placeholder.com/400x200',
    },
    {
        name: 'Candidato 2',
        description: 'Descrição do Candidato 2',
        image: 'https://via.placeholder.com/400x200',
    },
    {
        name: 'Candidato 2',
        description: 'Descrição do Candidato 2',
        image: 'https://via.placeholder.com/400x200',
    },
    {
        name: 'Candidato 2',
        description: 'Descrição do Candidato 2',
        image: 'https://via.placeholder.com/400x200',
    },
    {
        name: 'Candidato 2',
        description: 'Descrição do Candidato 2',
        image: 'https://via.placeholder.com/400x200',
    },
    {
        name: 'Candidato 2',
        description: 'Descrição do Candidato 2',
        image: 'https://via.placeholder.com/400x200',
    },
    {
        name: 'Candidato 2',
        description: 'Descrição do Candidato 2',
        image: 'https://via.placeholder.com/400x200',
    },
    // Adicione mais candidatos conforme necessário
]);

const handleSave = () => {
    isEditable.value = false;
    // Aqui, você pode adicionar a lógica para salvar as alterações do formulário
};
</script>

<style scoped>
/* Estilos adicionais, se necessário */
</style>