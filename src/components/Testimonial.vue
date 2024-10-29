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
    background: linear-gradient(90deg, #008A8E 0%, #026366 100%);
    padding: 4rem 2rem;
}

.testimonial-card {
    background-color: rgba(255, 255, 255, 0.9);
    border-radius: 16px;
    min-height: 230px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 20px;
    transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.testimonial-card:hover {
    transform: translateY(-5px);
    box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.1);
}

.testimonial-header {
    margin-bottom: 10px;
}

.testimonial-name {
    font-size: 1.2rem;
    font-weight: bold;
    color: #58592a;
}

.testimonial-text {
    font-size: 1rem;
    color: #58592a;
}

.btn-testimonials,
.btn-consulta {
    background-color: #f2784b;
    color: white;
    border-radius: 24px;
    margin: 0 10px;
}

.btn-testimonials:hover,
.btn-consulta:hover {
    background-color: #f2884b;
}
</style>