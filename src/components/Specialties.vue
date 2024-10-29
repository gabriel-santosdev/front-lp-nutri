<template>
    <v-container class="my-specialties" fluid>
        <v-row>
            <v-col cols="12">
                <h1 class="text">Minhas Especialidades</h1>
            </v-col>
        </v-row>

        <v-row>
            <v-col v-for="(specialty, index) in specialties" :key="index" cols="12" md="4">
                <v-card class="specialty-card" :style="{ animation: `fade-in 0.5s ease ${index * 0.1}s` }">
                    <v-img :src="specialty.image" height="200px" />
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
    background-color: #f5f5f5;
    padding: 100px 0 100px;
}

.text {
    display: flex;
    align-items: center;
    justify-content: center;
    color: black;
    margin-bottom: 30px;
}

.specialty-card {
    transition: transform 0.3s, box-shadow 0.3s;
    border-radius: 8px;
}

.specialty-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
}

.specialty-title {
    font-weight: bold;
    font-size: 1.5rem;
    color: #333;
}

.specialty-subtitle {
    font-weight: 400;
    color: #777;
}

@keyframes fade-in {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
</style>