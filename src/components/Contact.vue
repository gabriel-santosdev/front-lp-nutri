<template>
    <v-container class="contact-form" fluid>
        <v-row>
            <v-col cols="12">
                <v-card class="form-card">
                    <v-card-title class="text-center">
                        <h1 class="title">Contato</h1>
                    </v-card-title>
                    <v-card-text>
                        <v-form ref="form" v-model="valid" lazy-validation @submit.prevent="submitForm">
                            <v-text-field v-model="form.name" :rules="[rules.required]" label="Nome"
                                required></v-text-field>

                            <v-text-field v-model="form.email" :rules="[rules.required, rules.email]" label="E-mail"
                                required></v-text-field>

                            <v-text-field v-model="form.phone" :rules="[rules.required]" label="Telefone (WhatsApp)"
                                v-mask="'(##) #####-####'" required></v-text-field>

                            <v-textarea v-model="form.reason" :rules="[rules.required]" label="Motivo da Consulta"
                                required></v-textarea>

                            <v-select v-model="form.howHeard" :items="howHeardOptions" :rules="[rules.required]"
                                label="Como você conheceu nosso serviço?" required></v-select>

                            <v-btn type="submit" color="primary">Enviar</v-btn>
                        </v-form>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
import { mask } from 'vue-the-mask';

const valid = ref(false);
const form = ref({
    name: '',
    email: '',
    phone: '',
    reason: '',
    howHeard: ''
});

const rules = {
    required: (value: any) => !!value || 'Campo obrigatório.',
    email: (value: String) => {
        const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        return emailPattern.test(value) || 'E-mail inválido.';
    }
};

const howHeardOptions = [
    'Indicação',
    'Instagram',
    'Facebook',
    'Outros'
];

const submitForm = () => {
    if (valid.value) {
        const payload = { ...form.value };
        console.log('Formulário enviado:', payload);
        alert('Formulário enviado com sucesso!');
        resetForm();
    }
};

const resetForm = () => {
    form.value = {
        name: '',
        email: '',
        phone: '',
        reason: '',
        howHeard: ''
    };
    valid.value = false;
};
</script>

<style scoped>
.contact-form {
    background-color: #f9f9f9;
    padding: 40px 0;
}

.form-card {
    max-width: 600px;
    margin: auto;
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

.title {
    font-size: 2.5rem;
    margin: 0;
}

@media (max-width: 600px) {
    .title {
        font-size: 1.8rem;
    }
}
</style>