<template>
    <v-main class="background-about">
        <v-container>
            <v-row align="center" class="my-4">
                <v-col cols="12" md="5" class="d-flex justify-center position-relative">
                    <div class="profile-circle">
                        <v-img src="../../images/profile-lp-kay.png" class="rounded-circle" :max-width="450"
                            :max-height="450">
                        </v-img>
                        <div class="overlay">
                            <div class="social-icons">
                                <a href="#" class="social-icon">
                                    <v-icon size="45">
                                        mdi-facebook
                                    </v-icon>
                                </a>
                                <a href="#" class="social-icon">
                                    <v-icon size="45">
                                        mdi-alpha-x
                                    </v-icon>
                                </a>
                                <a href="#" class="social-icon">
                                    <v-icon size="45">
                                        mdi-instagram
                                    </v-icon>
                                </a>
                            </div>
                        </div>
                    </div>
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

<style lang="scss" scoped>
.profile-circle {
    position: relative;
    width: 450px;
    height: 450px;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;

    .rounded-circle {
        transition: transform 0.5s ease;
        border-radius: 100%;

    }

    &:hover .rounded-circle {
        transform: scale(1.1);
        background-color: rgba(166, 160, 75, 0.3);
    }

    .overlay {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        opacity: 0;
        transition: opacity 0.3s ease;
        z-index: 2;

        &:hover {
            opacity: 1;
        }

        .social-icons {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
            opacity: 1;
            transition: opacity 0.3s ease;
        }
    }
}

.social-icon {
    text-decoration: none;
    color: black;
    transition: color 0.3s;

    &:hover {
        color: blue;
    }
}
</style>