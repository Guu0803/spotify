<template>
    <div class="window-home">
        <div class="background-container" :style="background()">
            <div class="greeting">
                Bom dia
            </div>
            <div class="playlist-container">
                <div class="playlist-collumn">
                    <div class="playlist" v-on:mouseover="curtidas()" v-on:mouseleave="backgroundOff()"
                        v-on:click="toMusicasCurtidas()">
                        <img src="@/assets/musicas-curtidas.png" class="
                    img-thumb">
                        Músicas Curtidas
                        <div class="bnt-playlist-container" v-on:click.stop="playCurtidas()" :style="playingNowCurtidas()">
                            <span class="material-icons play-btn-playlist" v-if="play == 'musicasCurtidas'"
                                v-on:click.stop="pause()">
                                pause
                            </span>
                            <span class="material-icons play-btn-playlist" v-else>
                                play_arrow
                            </span>
                        </div>
                    </div>
                    <div class="playlist" v-on:mouseover="indie()" v-on:mouseleave="backgroundOff()" v-on:click="toIndie()">
                        <img src="@/assets/thumb-mix-indie.png" class="
                    img-thumb">
                        Mix Indie
                        <div class="bnt-playlist-container" v-on:click.stop="playIndie()" :style="playingNowIndie()">
                            <span class="material-icons play-btn-playlist" v-if="play == 'mixIndie'"
                                v-on:click.stop="pause()">
                                pause
                            </span>
                            <span class="material-icons play-btn-playlist" v-else>
                                play_arrow
                            </span>
                        </div>
                    </div>
                    <div class="playlist" v-on:mouseover="indieVibration()" v-on:mouseleave="backgroundOff()"
                        v-on:click="toIndieVibration()">
                        <img src="@/assets/indie.png" class="
                    img-thumb">
                        Indie Vibration
                        <div class="bnt-playlist-container" v-on:click.stop="playVibration()"
                            :style="playingNowVibration()">
                            <span class="material-icons play-btn-playlist" v-if="play == 'indieVibration'"
                                v-on:click.stop="pause()">
                                pause
                            </span>
                            <span class="material-icons play-btn-playlist" v-else>
                                play_arrow
                            </span>
                        </div>
                    </div>
                </div>
                <div class="playlist-collumn">
                    <div class="playlist" v-on:mouseover="country()" v-on:mouseleave="backgroundOff()"
                        v-on:click="toCountry()">
                        <img src="@/assets/country.png" class="
                    img-thumb">
                        Fucking Country Music
                        <div :style="playingNowCountry()" class="bnt-playlist-container" v-on:click.stop="playCountry()">
                            <span class="material-icons play-btn-playlist" v-if="play == 'countryMusic'"
                                v-on:click.stop="pause()">
                                pause
                            </span>
                            <span class="material-icons play-btn-playlist" v-else>
                                play_arrow
                            </span>
                        </div>
                    </div>
                    <div class="playlist" v-on:mouseover="sessions()" v-on:mouseleave="backgroundOff()"
                        v-on:click="toSessions()">
                        <img src="@/assets/session.png" class="
                    img-thumb">
                        Sessions
                        <div class="bnt-playlist-container" v-on:click.stop="playSessions()" :style="playingNowSession()">
                            <span class="material-icons play-btn-playlist" v-if="play == 'sessionMix'"
                                v-on:click.stop="pause()">
                                pause
                            </span>
                            <span class="material-icons play-btn-playlist" v-else>
                                play_arrow
                            </span>
                        </div>
                    </div>
                    <div class="playlist" v-on:mouseover="descobertas()" v-on:mouseleave="backgroundOff()"
                        v-on:click="toDescobertas()">
                        <img src="@/assets/descobertas.png" class="
                    img-thumb">
                        Descobertas da Semana
                        <div :style="playingNowDescobertas()" class="bnt-playlist-container"
                            v-on:click.stop="playDescobertas()">
                            <span class="material-icons play-btn-playlist" v-if="play == 'descobertasSemana'"
                                v-on:click.stop="pause()">
                                pause
                            </span>
                            <span class="material-icons play-btn-playlist" v-else>
                                play_arrow
                            </span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="recommendation-for">
            <div>
                Feito Para Gustavo Nogueira
            </div>
            <div class="show-more">
                Mostrar tudo
            </div>
        </div>
        <div class="recommendation">
            <div class="recommendation-card" v-on:click="toIndie()">
                <img src="@/assets/mix-indie.png" class="thumb-recommendation">
                <div class="title">
                    Mix Indie
                    <div class="content">
                        <div>
                            Corella,
                        </div>
                        <div>
                            Vistas,
                        </div>
                        <div>
                            Somebody's Chil...
                        </div>
                    </div>
                </div>
                <div class="play-container" :style="playingNowIndie()">
                    <div v-on:click.stop="playIndie()">
                        <span class="material-icons play-btn" v-if="play == 'mixIndie'" v-on:click.stop="pause()">
                            pause
                        </span>
                        <span class="material-icons play-btn" v-else>
                            play_arrow
                        </span>
                    </div>

                </div>
            </div>
            <div class="recommendation-card" v-on:click="toMixMetal()">
                <img src="@/assets/mix-metal.png" class="thumb-recommendation">
                <div class="title">
                    Mix Metal
                    <div class="content">
                        <div>
                            We're Wolves,
                        </div>
                        <div>
                            Bring Me The Horiz...
                        </div>
                    </div>
                </div>
                <div class="play-container" :style="playingNowMetal()">
                    <div v-on:click.stop="playMetal()">
                        <span class="material-icons play-btn" v-if="play == 'mixMetal'" v-on:click.stop="pause()">
                            pause
                        </span>
                        <span class="material-icons play-btn" v-else>
                            play_arrow
                        </span>
                    </div>
                </div>
            </div>
            <div class="recommendation-card" v-on:click="toDailyMix()">
                <img src="@/assets/daily-mix.png" class="thumb-recommendation">
                <div class="title">
                    Daily Mix 1
                    <div class="content">
                        <div>
                            Nothing But Thieves,
                        </div>
                        <div>
                            Two Door Cinema Cl...
                        </div>
                    </div>
                </div>
                <div class="play-container" :style="playingNowDaily()">
                    <div v-on:click.stop="playDaily()">
                        <span class="material-icons play-btn" v-if="play == 'mixDaily'" v-on:click.stop="pause()">
                            pause
                        </span>
                        <span class="material-icons play-btn" v-else>
                            play_arrow
                        </span>
                    </div>
                </div>
            </div>
            <div class="recommendation-card" v-on:click="toMixRelax()">
                <img src="@/assets/mix-relax.png" class="thumb-recommendation">
                <div class="title">
                    Mix Relax
                    <div class="content">
                        <div>
                            Dennis Lloyd,
                        </div>
                        <div>
                            Frank Ocean...
                        </div>
                    </div>
                </div>
                <div class="play-container"  :style="playingNowRelax()">
                    <div v-on:click.stop="playRelax()">
                        <span class="material-icons play-btn" v-if="play == 'mixRelax'" v-on:click.stop="pause()">
                            pause
                        </span>
                        <span class="material-icons play-btn" v-else>
                            play_arrow
                        </span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'homePage',
    data() {
        return {
            playlist: '',
            play: '',
            playingNow: ''
        }
    },
    methods: {
        playingNowMetal() {
            if (this.playingNow == 'mixMetal') {
                return 'display:block;'
            }
        },
        playingNowCurtidas() {
            if (this.playingNow == 'musicasCurtidas') {
                return 'display:block;'
            }
        },
        playingNowIndie() {
            if (this.playingNow == 'mixIndie') {
                return 'display:block;'
            }
        },
        playingNowVibration() {
            if (this.playingNow == 'indieVibration') {
                return 'display:block;'
            }
        },
        playingNowCountry() {
            if (this.playingNow == 'countryMusic') {
                return 'display:block;'
            }
        },
        playingNowDaily() {
            if (this.playingNow == 'mixDaily') {
                return 'display:block;'
            }
        },
        playingNowSession() {
            if (this.playingNow == 'sessionMix') {
                return 'display:block;'
            }
        },
        playingNowDescobertas() {
            if (this.playingNow == 'descobertasSemana') {
                return 'display:block;'
            }
        },
        playingNowRelax() {
            if (this.playingNow == 'mixRelax') {
                return 'display:block;'
            }
        },
        playCountry() {
            this.play = 'countryMusic'
            this.playingNow = 'countryMusic'
        },
        playDaily() {
            this.play = 'mixDaily'
            this.playingNow = 'mixDaily'
        },
        playRelax() {
            this.play = 'mixRelax'
            this.playingNow = 'mixRelax'
        },
        playMetal() {
            this.play = 'mixMetal'
            this.playingNow = 'mixMetal'
        },
        pause() {
            this.play = ''
        },
        playDescobertas() {
            this.play = 'descobertasSemana'
            this.playingNow = 'descobertasSemana'
        },
        playCurtidas() {
            this.play = 'musicasCurtidas'
            this.playingNow = 'musicasCurtidas'
        },
        playIndie() {
            this.play = 'mixIndie'
            this.playingNow = 'mixIndie'
        },
        playVibration() {
            this.play = 'indieVibration'
            this.playingNow = 'indieVibration'
        },
        playSessions() {
            this.play = 'sessionMix'
            this.playingNow = 'sessionMix'
        },
        toCountry() {
            this.$router.push('/country')
        },
        toSessions() {
            this.$router.push('/sessions')
        },
        toMusicasCurtidas() {
            this.$router.push('/musicas-curtidas')
        },
        toMixRelax() {
            this.$router.push('/mix-relax')
        },
        toMixMetal() {
            this.$router.push('/mix-metal')
        },
        toIndieVibration() {
            this.$router.push('/indie-vibration')
        },
        toDailyMix() {
            this.$router.push('/daily-mix')
        },
        toDescobertas() {
            this.$router.push('/descobertas-da-semana')
        },
        toIndie() {
            this.$router.push('/mix-indie')
        },
        indie() {
            this.playlist = 'indie'
        },
        curtidas() {
            this.playlist = 'curtidas'
        },
        indieVibration() {
            this.playlist = 'vibration'
        },
        country() {
            this.playlist = 'country'
        },
        sessions() {
            this.playlist = 'sessions'
        },
        descobertas() {
            this.playlist = 'descobertas'
        },
        backgroundOff() {
            this.playlist = ''
        },
        background() {
            if (this.playlist == 'indie') {
                return 'background-image: linear-gradient(to bottom, rgba(255, 20, 147, 0.7), rgba(255, 20, 147, 0.60), rgba(255, 20, 147, 0.50), rgba(255, 20, 147, 0.20), rgba(255, 20, 147, 0.10), var(--div-background));'
            }
            if (this.playlist == 'curtidas') {
                return 'background-image: linear-gradient(to bottom,  rgba(	31, 16, 79), rgba(31, 16, 79, 0.80), rgba(	31, 16, 79, 0.60), rgba(31, 16, 79, 0.30), rgba(31, 16, 79, 0.10), var(--div-background));'
            }
            if (this.playlist == 'country') {
                return 'background-image: linear-gradient(to bottom, rgba(184,20,20, 0.7), rgba(184,20,20, 0.60), rgba(184,20,20, 0.50), rgba(184,20,20, 0.20), rgba(184,20,20, 0.10), var(--div-background));'
            }
            if (this.playlist == 'vibration') {
                return 'background-image: linear-gradient(to bottom, rgba(237, 145, 33, 0.7), rgba(237 , 145 , 33, 0.60), rgba(237 , 145 , 33, 0.50), rgba(237 , 145 , 33, 0.20), rgba(237 , 145 , 33, 0.10), var(--div-background));'
            }
            if (this.playlist == 'sessions') {
                return 'background-image: linear-gradient(to bottom, rgba(114, 49, 114, 0.7), rgba(114, 49, 114, 0.60), rgba(114, 49, 114, 0.50), rgba(114, 49, 114, 0.20), rgba(114, 49, 114, 0.10), var(--div-background));'
            }
            if (this.playlist == 'descobertas') {
                return 'background-image: linear-gradient(to bottom, rgba(41,99,147, 0.7), rgba(41,99,147, 0.60), rgba(41,99,147, 0.50), rgba(41,99,147, 0.20), rgba(41,99,147, 0.10), var(--div-background));'
            }
        },
    },
}
</script>
<style scoped>
:root {
    --green: #1ed760;
    --font-color: #a7a7a7;
    --font-color-hover: #fff;
    --div-background: #121212;
    --div-background-2: #1a1a1a;
    --background-highlight: #242424;
    --background: #000;
    --background-hover: hsla(0, 0%, 100%, .07);
}

.background-container {
    padding: 1vw 1vw 0 1vw;
    border-radius: 10px 10px 0 0;
    transition: ease-in-out 200ms;

}

.greeting {
    color: var(--font-color-hover);
    font-size: 2em;
    font-weight: 700;
    letter-spacing: -2px;
    margin: 6vh 1vw 2vh 0;
}

.playlist-container {
    display: flex;
    width: 100%;
    gap: 1vw;

}

.playlist-collumn {
    display: flex;
    flex-direction: column;
    gap: 1vh;
    width: 100%;
}

.playlist {
    height: 10vh;
    border-radius: 5px;
    color: var(--font-color-hover);
    font-weight: 600;
    letter-spacing: -1px;
    display: flex;
    align-items: center;
    gap: 1vw;
    background: #a7a7a730;
    position: relative;
}

.bnt-playlist-container {
    display: none;
    right: 1vw;
    position: absolute;
}

.play-btn-playlist {
    padding: 1vh;
    background-color: #1ed760;
    border-radius: 50%;
    font-size: 2.5em;
    cursor: pointer;
    color: #000;
    box-shadow: 0px 25px 28px -11px rgba(0, 0, 0, 0.75);
}

.play-btn-playlist:hover {
    scale: 1.1;
    transition: ease-in-out 100ms;
}

.playlist:hover {
    background: #a7a7a760;
    cursor: pointer;
}

.playlist:hover>.bnt-playlist-container {
    display: block;
}

.img-thumb {
    height: 100%;
    border-radius: 5px;
}

.recommendation-for {
    font-size: 1.4em;
    color: var(--font-color-hover);
    font-weight: 700;
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 4vh 1vw;
}

.show-more {
    color: var(--font-color);
    font-size: 0.5em;
}

.recommendation-for>div:hover {
    text-decoration: underline 2px;
    cursor: pointer;
}

.recommendation {
    display: flex;
    gap: 1.5vw;
    align-items: center;
    margin: 0 1vw 5vh 1vw;
}

.recommendation-card {
    position: relative;
    display: flex;
    flex-direction: column;
    cursor: pointer;
    height: 40vh;
    width: 20vw;
    border-radius: 5px;
    background-color: var(--div-background-2);
    align-items: center;
}

.recommendation-card:hover {
    background-color: var(--background-highlight);
    transition: ease-in-out;
}


.play-btn {
    padding: 1vh;
    background-color: #1ed760;
    border-radius: 50%;
    font-size: 2em;
    cursor: pointer;
    position: absolute;
    top: 16vh;
    right: 2vw;
    z-index: 2;
    box-shadow: 0px 25px 28px -11px rgba(0, 0, 0, 0.75);
}

.play-btn:hover {
    scale: 1.1;
    transition: ease-in-out;
}

.play-container {
    position: absolute;
    width: 100%;
    height: 98%;
    z-index: 0;
    display: none;
}

.recommendation-card:hover>.play-container {
    display: block;
}

.thumb-recommendation {
    height: 23vh;
    width: 11vw;
    margin: 1vw 0;
    border-radius: 5px;
}

.title {
    color: var(--font-color-hover);
    font-weight: 700;
    width: 11vw;
}

.content {
    font-size: 0.8em;
    font-weight: 600;
    color: var(--font-color);
    margin-top: 1vh;
    line-height: 3vh;
    display: flex;
    gap: 1vh;
    flex-wrap: wrap;
}
</style>
