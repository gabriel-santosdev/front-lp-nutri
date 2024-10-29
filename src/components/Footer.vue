<template>
    <v-footer color="#6F4D5A" class="footer">
        <v-container>
            <v-row align="center" justify="space-between">
                <v-col class="footer-name">
                    <h2 class="white--text">Kayanne Morais</h2>
                </v-col>
                <v-col class="footer-right" align="end">
                    <v-row justify="end">
                        <v-col cols="auto">
                            <v-icon @click="openLink('https://www.facebook.com')"
                                class="social-icon">mdi-facebook</v-icon>
                        </v-col>
                        <v-col cols="auto">
                            <v-icon @click="openLink('https://www.instagram.com')"
                                class="social-icon">mdi-instagram</v-icon>
                        </v-col>
                        <v-col cols="auto">
                            <v-icon @click="openLink('https://www.linkedin.com')"
                                class="social-icon">mdi-linkedin</v-icon>
                        </v-col>
                    </v-row>
                    <p class="white--text footer-address">Endereço: Rua Exemplo, 123, Cidade, Estado</p>
                    <v-btn @click="scrollToTop" color="primary" dark prepend-icon="mdi-arrow-up">
                        Voltar ao Topo
                    </v-btn>
                </v-col>
            </v-row>
            <v-divider class="my-2"></v-divider>
            <v-row justify="center">
                <p class="white--text">© {{ currentYear }} Todos os direitos reservados.<br> Desenvolvido por <a>Gabriel
                        Santos | GS Software</a></p>
            </v-row>
        </v-container>
    </v-footer>
</template>

<script setup>
import { ref } from 'vue';

const currentYear = ref(new Date().getFullYear());

const openLink = (url) => {
    window.open(url, '_blank');
};

const scrollToTop = () => {
    window.scrollTo({
        top: 0,
        behavior: 'smooth'
    });
};
</script>

<style scoped>
.footer {
    padding: 20px 0;
}

.footer-name {
    font-weight: bold;
}

.footer-right {
    text-align: right;
}

.footer-address {
    margin-top: 5px;
}

.social-icon {
    font-size: 24px;
    color: white;
    cursor: pointer;
    transition: color 0.3s;
}

.social-icon:hover {
    color: #ccc;
}
</style>