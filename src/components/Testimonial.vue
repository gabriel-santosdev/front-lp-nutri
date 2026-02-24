<template>
    <v-container fluid class="testimonial-section">
        <v-row class="justify-center">
            <v-col cols="12" md="10">
                <v-row>
                    <v-col v-for="(testimonial, index) in testimonials" :key="index" cols="12" md="4" class="d-flex">
                        <v-card class="testimonial-card" outlined>
                            <v-card-text>
                                <div class="testimonial-header d-flex align-center justify-space-between">
                                    <!-- Substituindo o avatar por um ícone -->
                                    <v-icon size="40" color="#A6A04B">mdi-account</v-icon>
                                    <v-icon size="20">mdi-google</v-icon>
                                </div>
                                <div class="testimonial-content">
                                    <h3 class="testimonial-name">{{ testimonial.name }}</h3>
                                    <v-rating value="5" dense readonly color="orange" />
                                    <p class="testimonial-text">{{ testimonial.feedback }}</p>
                                </div>
                            </v-card-text>
                        </v-card>
                    </v-col>
                </v-row>

                <v-row class="justify-center mt-4">
                    <v-btn class="btn-testimonials" large prepend-icon="mdi-more">
                        Ver todos depoimentos
                    </v-btn>
                </v-row>
            </v-col>
        </v-row>
    </v-container>
</template>

<script setup>
import { ref } from 'vue'

const testimonials = ref([
    {
        name: 'Michele Brito',
        feedback:
            'Uma excelente profissional, atenciosa em todos os detalhes. Se você se sente perdido e está a procura de um bom profissional, com certeza é ela. Super recomendo!',
    },
    {
        name: 'Nancy Amaral',
        feedback:
            'Profissional super dedicada, pontual e oferece um atendimento único. Estou muito satisfeita com suas orientações e indico para todos.',
    },
    {
        name: 'Ana Paula Felix',
        feedback:
            'A melhor Nutri da vida! Tratamento humanizado, cardápio e suplementos totalmente personalizados.',
    },
    {
        name: 'Luciana Regina Pinto',
        feedback:
            'Kayanne é uma profissional muito atenciosa. Suas recomendações têm contribuído para meu objetivo.',
    },
    {
        name: 'Danielle Alves',
        feedback: 'Muito atenciosa e competente. Recomendo!',
    },
])
</script>

<style scoped>
.testimonial-section {
    background: linear-gradient(180deg, #ffffff 0%, var(--color-neutral) 100%);
    padding: 3.5rem 1.2rem;
}

.testimonial-card {
    background-color: var(--card-bg);
    border-radius: 14px;
    min-height: 200px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 22px;
    transition: transform 0.28s ease, box-shadow 0.28s ease;
    border: 1px solid rgba(0, 0, 0, 0.04);
}

.testimonial-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 12px 28px rgba(0, 0, 0, 0.06);
}

.testimonial-header {
    margin-bottom: 8px;
}

.testimonial-name {
    font-size: 1.05rem;
    font-weight: 600;
    color: var(--color-primary);
}

.testimonial-text {
    font-size: 0.98rem;
    color: var(--muted-text);
}

.btn-testimonials,
.btn-consulta {
    background: var(--color-primary);
    color: white;
    border-radius: 999px;
    margin: 0 8px;
}

.btn-testimonials:hover,
.btn-consulta:hover {
    background: var(--color-accent);
}
</style>