<template>
    <v-app>

        <v-app-bar flat class="appbar">

            <v-app-bar-nav-icon @click="drawer = !drawer" class="d-md-none"></v-app-bar-nav-icon>

            <v-toolbar-title class="brand">Kayanne Morais</v-toolbar-title>

            <v-spacer></v-spacer>

            <v-btn text="true" class="d-none d-md-flex accent-link">Início</v-btn>
            <v-btn text="true" class="d-none d-md-flex accent-link">Sobre</v-btn>
            <v-btn text="true" class="d-none d-md-flex accent-link">Contato</v-btn>
        </v-app-bar>

        <!-- Menu lateral (drawer) para mobile -->
        <v-navigation-drawer v-model="drawer" app temporary class="drawer">
            <v-list>
                <v-list-item>
                    <v-list-item-title>Menu</v-list-item-title>
                </v-list-item>

                <v-divider></v-divider>

                <v-list-item link>
                    <v-list-item-title>Home</v-list-item-title>
                </v-list-item>

                <v-list-item link>
                    <v-list-item-title>About</v-list-item-title>
                </v-list-item>

                <v-list-item link>
                    <v-list-item-title>Contact</v-list-item-title>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>

        <!-- Conteúdo principal -->
        <About />
        <Whensearch />
        <Testimonial />
        <Specialties />
        <Contact />
    </v-app>
</template>

<script setup lang="ts">
import { ref } from 'vue';

import About from './About.vue';
import Whensearch from './Whensearch.vue';
import Testimonial from './Testimonial.vue';
import Specialties from './Specialties.vue';
import Contact from './Contact.vue';

const drawer = ref(false);
</script>

<style scoped>
.appbar {
    background: rgba(255, 255, 255, 0.9);
    border-bottom: 1px solid rgba(0, 0, 0, 0.06);
}

.brand {
    color: var(--text-color);
    font-weight: 600;
}

.accent-link {
    color: var(--color-primary) !important;
    font-weight: 600;
}

.drawer {
    background: linear-gradient(180deg, var(--color-neutral), #ffffff);
    color: var(--text-color);
}

.v-list-item-title {
    color: var(--text-color) !important;
}
</style>
