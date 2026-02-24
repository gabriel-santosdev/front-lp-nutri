<template>
    <v-container class="contact-form" fluid>
        <v-row>
            <v-col cols="12">
                <v-card class="form-card">
                    <v-card-title class="text-center">
                        <h1 class="title">Contato</h1>
                    </v-card-title>
                    <v-card-text>
                        <v-form ref="formRef" v-model="valid" lazy-validation @submit.prevent="submitForm">
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

                            <v-btn type="submit" class="btn-primary">Enviar</v-btn>
                        </v-form>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const valid = ref(false);
const formRef = ref<any>(null);
const form = ref({
    name: '',
    email: '',
    phone: '',
    reason: '',
    howHeard: ''
});

const rules = {
    required: (value: any) => !!value || 'Campo obrigatório.',
    email: (value: string) => {
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

    // Verifica se formRef foi montado corretamente antes de chamar resetValidation
    if (formRef.value) {
        formRef.value.resetValidation();
    }

    valid.value = false;
};
</script>

<style scoped>
.contact-form {
    background: linear-gradient(180deg, #ffffff 0%, var(--color-neutral) 100%);
    padding: 56px 0;
}

.form-card {
    max-width: 640px;
    margin: auto;
    border-radius: 12px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.06);
    background: var(--card-bg);
    border: 1px solid rgba(0, 0, 0, 0.04);
}

.title {
    font-size: 2rem;
    margin: 0;
    color: var(--color-primary);
}

/* use global .btn-primary from index.scss */

@media (max-width: 600px) {
    .title {
        font-size: 1.6rem;
    }
}
</style>