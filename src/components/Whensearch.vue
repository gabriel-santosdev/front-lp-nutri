<template>
    <v-container class="nutrition-section" fluid>
        <v-row class="justify-center">
            <v-col cols="12" md="8">
                <v-card class="transparent-card" elevation="0">
                    <v-card-title class="title text-center">
                        Quando procurar uma nutricionista?
                    </v-card-title>

                    <v-card-text>
                        <v-row class="gy-4">
                            <v-col v-for="(option, index) in options" :key="index" cols="12" md="6">
                                <v-card class="option-card" outlined>
                                    <v-card-text class="option">
                                        {{ option }}
                                    </v-card-text>
                                </v-card>
                            </v-col>
                        </v-row>
                    </v-card-text>

                    <v-card-actions class="actions justify-center">
                        <v-btn class="whatsapp-btn" large @click="openWhatsApp">
                            <v-icon left>mdi-whatsapp</v-icon>
                            Agendar uma consulta
                        </v-btn>
                    </v-card-actions>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const options = ref([
    'Plano alimentar individualizado para suas necessidades',
    'Plano de cuidados para o gerenciamento de doenças e desequilíbrios nutricionais',
    'Emagrecimento com olhar integrado',
    'Plano de cuidados para saúde, bem-estar e vitalidade',
    'Saúde digestiva e intestinal',
    'Saúde da mulher',
    'Fertilidade e gestação saudável',
    'Saúde mental',
    'Vegetarianismo',
])

const openWhatsApp = () => {
    const whatsappLink = 'https://wa.me/5551999999999' // Substitua pelo número correto
    window.open(whatsappLink, '_blank')
}
</script>

<style scoped>
.nutrition-section {
    background: linear-gradient(135deg, #A6A04B, #D4D087, #ECE9C2);
    padding: 4rem 2rem;
}

.title {
    font-size: 2.2rem;
    color: #58592a;
    font-weight: bold;
    margin-bottom: 2rem;
}

.transparent-card {
    background-color: transparent;
}

.option-card {
    background-color: rgba(255, 255, 255, 0.8);
    border-radius: 10px;
    transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.option-card:hover {
    transform: translateY(-5px);
    box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.1);
}

.option {
    font-size: 1.2rem;
    color: #58592a;
}

.actions {
    margin-top: 2rem;
}

.whatsapp-btn {
    background: linear-gradient(90deg, #008A8E 0%, #026366 100%);
    color: white;
    font-weight: bold;
    border-radius: 24px;
}

.whatsapp-btn:hover {
    background-color: #f2884b;
}

@media (max-width: 960px) {
    .nutrition-section {
        padding: 2rem 1rem;
    }

    .title {
        font-size: 1.8rem;
    }
}
</style>