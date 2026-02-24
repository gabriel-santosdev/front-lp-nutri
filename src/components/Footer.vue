<template>
    <v-footer class="footer">
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
                    <p class="footer-address">Endereço: Rua Exemplo, 123, Cidade, Estado</p>
                    <v-btn @click="scrollToTop" class="btn-topo" prepend-icon="mdi-arrow-up">
                        Voltar ao Topo
                    </v-btn>
                </v-col>
            </v-row>
            <v-divider class="my-2"></v-divider>
            <v-row justify="center">
                <p>© {{ currentYear }} Todos os direitos reservados.<br> Desenvolvido por <a>Gabriel
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
    padding: 28px 0;
    background: transparent;
    border-top: 1px solid rgba(0, 0, 0, 0.06);
}

.footer-name {
    font-weight: 600;
    color: var(--text-color);
}

.footer-right {
    text-align: right;
}

.footer-address {
    margin-top: 6px;
    color: var(--muted-text);
}

.social-icon {
    font-size: 22px;
    color: var(--muted-text);
    cursor: pointer;
    transition: color 0.18s ease, transform 0.18s ease;
}

.social-icon:hover {
    color: var(--color-primary);
    transform: translateY(-3px);
}

.btn-topo {
    background: transparent;
    border: 1px solid rgba(0, 0, 0, 0.06);
    color: var(--text-color);
    border-radius: 20px;
}
</style>
