<template>
    <v-main class="background-about">
        <v-container>
            <v-row align="center" class="my-4">
                <v-col cols="12" md="5" class="d-flex justify-center">
                    <v-img src="src\assets\images\profile-lp-kay.png" class="rounded-circle" :max-width="450"
                        :max-height="450"></v-img>
                </v-col>
                <v-col cols="12" md="7">
                    <h2>Sobre Mim</h2>
                    <p>
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                        Integer nec odio. Praesent libero. Sed cursus ante dapibus diam.
                        Sed nisi. Nulla quis sem at nibh elementum imperdiet.
                        Duis sagittis ipsum. Praesent mauris.
                    </p>
                </v-col>
            </v-row>
        </v-container>
    </v-main>
</template>
<script lang="ts" scoped>
import profileImage from '../assets/images/profile-lp-w-back.jpeg';
</script>
<style lang="scss" scoped>
.rounded-circle {
    background-color: rgba(166, 160, 75, 0.3);
    border-radius: 100%;
}
</style>