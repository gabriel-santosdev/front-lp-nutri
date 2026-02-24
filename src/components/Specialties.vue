<template>
    <v-container class="my-specialties" fluid>
        <v-row>
            <v-col cols="12">
                <h1 class="text">Minhas Especialidades</h1>
            </v-col>
        </v-row>

        <v-row>
            <v-col v-for="(specialty, index) in specialties" :key="index" cols="12" md="4">
                <v-card class="specialty-card card-soft" :style="{ animation: `fade-in 0.5s ease ${index * 0.1}s` }">
                    <v-img class="specialty-img" :src="specialty.image" height="160px" />
                    <v-card-title class="specialty-title">{{ specialty.title }}</v-card-title>
                    <v-card-subtitle class="specialty-subtitle">{{ specialty.subtitle }}</v-card-subtitle>
                    <v-card-text>
                        <p>{{ specialty.description }}</p>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    data() {
        return {
            specialties: [
                {
                    title: "Nutrição Esportiva",
                    subtitle: "Aprimorando seu desempenho",
                    description: "Desenvolvo planos nutricionais específicos para atletas e entusiastas do esporte, focando em macronutrientes que maximizam a performance, recuperação e resistência durante os treinos e competições.",
                    image: "../../images/nutri_esportiva.png"
                },
                {
                    title: "Nutrição Funcional",
                    subtitle: "Saúde em primeiro lugar",
                    description: "Trabalho com uma abordagem que utiliza alimentos para ajudar na prevenção de doenças e promover a saúde geral, adaptando a dieta às necessidades individuais e ao estilo de vida.",
                    image: "../../images/nutri_funcional.png"
                },
                {
                    title: "Nutrição Clínica",
                    subtitle: "Cuidando da sua saúde",
                    description: "Ofereço atendimento individualizado e suporte nutricional para diversas condições de saúde, incluindo diabetes, hipertensão e alergias alimentares, visando melhorar a qualidade de vida dos meus pacientes.",
                    image: "../../images/nutri_clinica.png"
                }
            ]
        };
    }
};
</script>

<style scoped>
.my-specialties {
    background: #ffffff;
    padding: 6rem 0 6rem;
}

.text {
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--text-color);
    margin-bottom: 2rem;
}

.specialty-card {
    transition: transform 0.28s ease, box-shadow 0.28s ease;
    border-radius: 12px;
    background: var(--card-bg);
    border: 1px solid rgba(0, 0, 0, 0.04);
    padding-bottom: 0.75rem;
    margin-bottom: 1rem;
}

.specialty-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 12px 30px rgba(0, 0, 0, 0.06);
}

.specialty-title {
    font-weight: 600;
    font-size: 1.25rem;
    color: var(--color-primary);
}

.specialty-subtitle {
    font-weight: 400;
    color: var(--muted-text);
}

.specialty-card .specialty-img {
    height: 160px;
    object-fit: contain;
    padding: 12px;
}

.specialty-card v-card-text p {
    margin: 0;
    color: var(--muted-text);
}

@keyframes fade-in {
    from {
        opacity: 0;
        transform: translateY(6px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
</style>