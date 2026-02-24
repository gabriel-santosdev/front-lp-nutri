<template>
    <v-main class="background-about">
        <v-container>
            <v-row align="center" class="my-4">
                <v-col cols="12" md="5" class="d-flex justify-center position-relative">
                    <div class="profile-circle">
                        <v-img src="../../images/foto_port_nutri.png" class="rounded-circle" :max-width="450"
                            :max-height="450">
                        </v-img>
                        <div class="overlay">
                            <div class="social-icons">
                                <div class="social-pill">
                                    <a href="https://www.instagram.com/" target="_blank" rel="noopener"
                                        aria-label="Instagram" class="social-icon">
                                        <v-icon size="20">mdi-instagram</v-icon>
                                    </a>
                                    <a href="https://api.whatsapp.com/send?phone=5511961960633&text=Olá%20!%20Gostaria%20de%20agendar%20uma%20consulta."
                                        target="_blank" rel="noopener" aria-label="WhatsApp"
                                        class="social-icon whatsapp">
                                        <v-icon size="20">mdi-whatsapp</v-icon>
                                    </a>
                                </div>
                            </div>
                        </div>
                    </div>
                </v-col>
                <v-col cols="12" md="7">
                    <h2>Sobre Mim</h2>
                    <p>
                        Olá — sou Kayanne Morais, nutricionista clínica com formação em nutrição
                        funcional e atenção à performance. Atendo de maneira individualizada,
                        com foco em hábitos sustentáveis, educação alimentar e acompanhamento
                        para perda de peso saudável, saúde digestiva e bem-estar geral.
                    </p>
                </v-col>
            </v-row>
        </v-container>
    </v-main>
</template>

<style lang="scss" scoped>
.background-about {
    background: linear-gradient(180deg, var(--color-neutral) 0%, rgba(255, 255, 255, 0) 60%);
    padding: 6rem 0;
}

.profile-circle {
    position: relative;
    width: 340px;
    height: 340px;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    border-radius: 50%;
    box-shadow: 0 6px 30px rgba(0, 0, 0, 0.06);

    .rounded-circle {
        transition: transform 0.45s ease, filter 0.45s ease;
        border-radius: 50%;
        object-fit: cover;
    }

    &:hover .rounded-circle {
        transform: scale(1.03);
        filter: saturate(1.03) contrast(1.02);
    }

    .overlay {
        position: absolute;
        inset: 0;
        display: flex;
        justify-content: center;
        align-items: end;
        padding-bottom: 14px;
        pointer-events: none;

        .social-pill {
            pointer-events: auto;
            display: inline-flex;
            gap: 10px;
            align-items: center;
            background: rgba(255, 255, 255, 0.92);
            padding: 6px 10px;
            border-radius: 999px;
            box-shadow: 0 8px 22px rgba(0, 0, 0, 0.06);
            border: 1px solid rgba(0, 0, 0, 0.04);
            backdrop-filter: blur(4px);
        }
    }
}

.social-icon {
    text-decoration: none;
    color: var(--color-primary);
    transition: color 0.18s ease, transform 0.18s ease;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 34px;
    height: 34px;
    border-radius: 8px;

    v-icon {
        line-height: 1;
    }

    &:hover {
        color: var(--color-accent);
        transform: translateY(-3px);
    }
}

h2 {
    font-weight: 600;
    margin-bottom: 0.75rem;
}

p {
    color: var(--muted-text);
    line-height: 1.7;
}

.social-icon.whatsapp {
    color: #fff;
    background: linear-gradient(90deg, rgba(170, 175, 153, 1), var(--color-soft-green));
    width: 36px;
    height: 36px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    border-radius: 8px;
    box-shadow: 0 6px 18px rgba(0, 0, 0, 0.08);
}

@media (max-width: 960px) {
    .profile-circle {
        width: 300px;
        height: 300px;
    }

    .social-pill {
        padding: 5px 8px;
        gap: 8px;
    }

    .social-icon {
        width: 30px;
        height: 30px;
    }

    .social-icon.whatsapp {
        width: 32px;
        height: 32px;
    }
}

@media (max-width: 420px) {

    /* hide overlay on very small screens to avoid covering the image */
    .social-pill {
        display: none;
    }

    .profile-circle {
        width: 220px;
        height: 220px;
    }
}
</style>