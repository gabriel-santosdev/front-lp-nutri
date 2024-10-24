<template>
    <v-btn fab color="green" class="whatsapp-button" @click="openWhatsApp">
        <v-icon>mdi-whatsapp</v-icon>
        &nbsp;
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
.whatsapp-button {
    position: fixed;
    bottom: 16px;
    right: 16px;
    z-index: 1000;
}
</style>