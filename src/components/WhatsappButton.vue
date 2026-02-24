<template>
    <v-btn class="btn-primary whatsapp-floating" elevation="4" rounded @click="openWhatsApp">
        <v-icon left>mdi-whatsapp</v-icon>
        Agendar uma consulta
    </v-btn>
</template>

<script setup>
const openWhatsApp = () => {
    const phoneNumber = '5511961960633';
    const message = 'Olá! Gostaria de agendar uma consulta.';
    const url = `https://api.whatsapp.com/send?phone=${phoneNumber}&text=${encodeURIComponent(message)}`;
    window.open(url, '_blank');
};
</script>

<style scoped>
.whatsapp-floating {
    position: fixed;
    bottom: 24px;
    right: 24px;
    z-index: 1000;
    /* use soft green from palette for the floating button */
    background: linear-gradient(90deg, var(--color-green-strong), var(--color-soft-green)) !important;
    color: #fff !important;
    padding: 8px 14px !important;
    min-width: 170px;
    border-radius: 28px;
    display: inline-flex;
    align-items: center;
    gap: 10px;
    box-shadow: 0 8px 22px rgba(68, 83, 57, 0.10);
}

.whatsapp-floating:hover {
    transform: translateY(-4px);
}

/* ensure v-icon inside the button is visible */
.whatsapp-floating .v-icon,
.whatsapp-floating v-icon {
    color: #fff !important;
}
</style>