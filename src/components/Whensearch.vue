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
    background: #ffffff;
    padding: 3.5rem 1rem;
}

.title {
    font-size: 1.9rem;
    color: var(--color-primary);
    font-weight: 600;
    margin-bottom: 1.4rem;
}

.transparent-card {
    background-color: transparent;
}

.option-card {
    background-color: var(--card-bg);
    border-radius: 10px;
    transition: transform 0.28s ease, box-shadow 0.28s ease;
    border: 1px solid rgba(0, 0, 0, 0.04);
}

.option-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 12px 30px rgba(0, 0, 0, 0.06);
}

.option {
    font-size: 1.05rem;
    color: var(--muted-text);
}

.actions {
    margin-top: 1.6rem;
}

.whatsapp-btn {
    background: linear-gradient(90deg, var(--color-accent), var(--color-primary));
    color: white;
    font-weight: 600;
    border-radius: 28px;
    padding: 10px 18px;
    box-shadow: 0 10px 26px rgba(174, 115, 82, 0.12);
    display: inline-flex;
    align-items: center;
    gap: 8px;
}

.whatsapp-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 14px 34px rgba(174, 115, 82, 0.14);
}

@media (max-width: 960px) {
    .nutrition-section {
        padding: 2rem 1rem;
    }

    .title {
        font-size: 1.5rem;
    }
}
</style>