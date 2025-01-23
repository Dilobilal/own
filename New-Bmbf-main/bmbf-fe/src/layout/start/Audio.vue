<template>
  <div
      class="container d-flex justify-content-center align-items-center"
  >
    <div class=" element d-flex flex-column align-items-center ">
      <div class="row my-5 icon-txt">
        <div class="col-sm-2 d-flex icon">
          <i class="bi bi-volume-up"></i>
        </div>
        <div class="col-lg sprache d-flex align-items-center ">
          <h3>Audio</h3>
        </div>
      </div>
      <div class="">
        <div class="row">
          <div class="aud-text">
            <div class="beisp-txt">
              <span> Beispiel </span>
            </div>
            <div
                class="beisp-audio d-flex justify-content-center align-items-center"
            >
              <div class="audio d-flex align-items-center">
                <div class="audio-icon">
                  <button class="btn-audio" @click="runsound">
                    <i class="fa-solid fa-play"></i>
                  </button>
                </div>
                <div class="audio-wave">
                  <div class="boxContainer">
                    <div
                        v-for="(item, index) in (this.isrunning)?boxsgif:boxsnotgif"
                        :key="index"
                        :class="item"
                    ></div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div
            class="d-flex justify-content-center align-items-center flex-column my-5"
        >
        </div>
      </div>
      <div class="settings d-flex row">
        <div class="d-flex col-7 d-flex-right">
          <div class="set-txt ">
            <span> Lautstärke </span>
          </div>
          <div class="d-flex d-flex-right">
            <div class="audio-settings ">
              <div class="slider-container">
                <div class="vertical-line"></div> <!-- Linke vertikale Linie -->
                <input
                    :value="audioLevel"
                    @input="updateAudioLevel"
                    type="range"
                    min="0"
                    max="100"
                    step="25"
                    class="slider"
                />
                <div class="vertical-line"></div> <!-- Rechte vertikale Linie -->
              </div>
              <div class="level-display" :style="{ left: levelLocal+ '%'}">{{ audioLevel }}</div>
            </div>
          </div>
        </div>
        <div class="d-flex col-7 d-flex-right">
          <div class="set-txt ">
            <span> Vorlese - <br> Geschwindigkeit </span>
          </div>
          <div class="speed-control d-flex d-flex-right">
            <button class="speed-btn" :class="{ active: activeSpeed === 1 }" @click="setSpeed(1)">
              <span class="speed-number" :class="{ active: activeSpeed === 1 }">1x</span>
            </button>
            <button class="speed-btn" :class="{ active: activeSpeed === 1.5 }" @click="setSpeed(1.5)">
              <span class="speed-number" :class="{ active: activeSpeed === 1.5 }">1,5x</span>
            </button>
            <button class="speed-btn" :class="{ active: activeSpeed === 2 }" @click="setSpeed(2)">
              <span class="speed-number" :class="{ active: activeSpeed === 2 }">2x</span>
            </button>
          </div>
        </div>
      </div>
      <div class="pagination p-element mx-5  ">
        <ul>
          <a href="#">
            <li></li>
          </a>
          <a href="#">
            <li></li>
          </a>
          <a href="#">
            <li></li>
          </a>
          <a href="#">
            <li></li>
          </a>
          <a class="is-active" href="#">
            <li></li>
          </a>
          <a href="#">
            <li></li>
          </a>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import {Howl, Howler} from "../../../node_modules/howler/dist/howler.js";

export default {
  name: "Audio",
  data() {
    return {
      levelLocal: 50,
      activeSpeed: 1, // Standardgeschwindigkeit
      audioLevel: 50, // Startwert in der Mitte
      sound: null, // The Howl instance
      volume: 0.5,
      isrunning: false,
      boxsgif: [
        "box box1",
        "box box2",
        "box box3",
        "box box4",
        "box box5",
        "box box6",
        "box box7",
        "box box8",
        "box box9",
        "box box10",
        "box box1",
        "box box2",
        "box box3",
        "box box4",
        "box box5",
        "box box6",
        "box box7",
        "box box8",
        "box box9",
        "box box10",
      ],
      boxsnotgif: [
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
        "box ",
      ],
    };
  },
  methods: {
    setSpeed(speed) {
      this.activeSpeed = speed;
    },
    updateAudioLevel(event) {
      this.audioLevel = Number(event.target.value); // Update audioLevel manually
      this.setVolume(); // Call setVolume to handle any additional logic
    },
    runsound() {
      if (!this.isrunning) {
        this.sound.play();
        this.isrunning = true;
      } else {
        this.sound.pause();
        this.isrunning = false;
      }
    },
    setVolume() {
      if (this.audioLevel === 0) {
        this.levelLocal = this.audioLevel - 42;
      } else if (this.audioLevel === 25) {
        this.levelLocal = this.audioLevel - 46;

      } else if (this.audioLevel === 50) {
        this.levelLocal = this.audioLevel - 49;
      } else if (this.audioLevel === 75) {
        this.levelLocal = this.audioLevel - 51;
      } else if (this.audioLevel === 100) {
        this.levelLocal = this.audioLevel - 57;
      }
      this.sound.volume(this.audioLevel / 100); // Update volume
    },
    initvolume() {
      this.levelLocal = this.audioLevel - 51;
    }
  },
  mounted() {
    // Initialize Howl instance
    this.sound = new Howl({
      src: [require("@/assets/sound.mp3")], // Adjust to your audio file path
      volume: this.volume, // Set initial volume
    });
    this.initvolume();
    this.setVolume();
  },
};
</script>

<style scoped>


.bi {
  font-size: 120px;
}

.element {
  margin-top: 676px;
  width: 1720px;
  height: 2499px;
  flex-shrink: 0;
  border-radius: 30px;
  background: #DEF0FC;
}

.sprache {
  position: relative;
  padding-left: 60px;
}

h3 {
  color: #000;
  font-size: 90px;
  font-style: normal;
  font-weight: 800;
  line-height: 95.89%; /* 86.301px */
}

.beisp-audio {
  margin-top: 179px;
  width: 100%;
  height: 187px;
}

.aud-text {
  background: black;
  margin-top: 237px;
  height: 540px;
  width: 1288px;
  border-radius: 30px;
}

.beisp-txt {
  margin-top: 44px;
}

.d-flex-right {
  justify-content: flex-end; /* Element nach rechts schieben */
  width: 100%; /* Elterncontainer in voller Breite */
}

.audio {
  height: 100%;
  width: 932px;
  border-radius: 100px;
  border: 4px solid #000;
  background: #DEF0FC;
  display: flex;
  align-items: center;
  padding: 10px 20px;
  position: relative;
  overflow: hidden;
}

.aud-text span {
  color: #DEF0FC;
  font-size: 40px;
  font-style: normal;
  font-weight: 680;
  line-height: 26.784px;
}

.audio-icon i {
  margin-left: 40px;
}

.icon-txt {
  width: 100%;
}

.icon {
  display: flex;
  justify-content: flex-end;
  width: 410px;
}


.btn-audio {
  border: none;
  background: transparent;
  cursor: pointer;
}


.settings {
  margin-top: 237px;
  width: 1284.27px;
  height: 330px;
}

.set-txt {
  margin-top: 20px;
}

.set-txt span {
  color: #000;
  font-size: 55px;
  font-style: normal;
  font-weight: 420;
  line-height: 26.784px;
}

.audio-settings {

  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  width: 717px;
  height: 110px;
  padding-left: 100px;
}

.slider {
  -webkit-appearance: none;
  width: 100%; /* Platz für die vertikalen Linien abziehen */
  height: 3px;
  background: #000;
  border-radius: 5px;
  outline: none;
  cursor: pointer;
}

.vertical-line {
  width: 3px; /* Breite der vertikalen Linie */
  height: 30px; /* Höhe der Linie */
  background: #000; /* Farbe der Linie */
}

.slider-container {
  position: relative;
  display: flex;
  align-items: center;
  width: 100%;
}


.slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 53.895px;
  height: 29px;
  border-radius: 100px;
  background: #000;
  cursor: pointer;
}

.slider::-moz-range-thumb {
  width: 20px;
  height: 20px;
  background: #000;
  border-radius: 50%;
  cursor: pointer;
}

.level-display {


  position: relative;
  top: -80px;
  color: #000;
  font-size: 50px;
  font-style: normal;
  font-weight: 420;
  line-height: 26.784px; /* 53.568% */
  width: 71.577px;
}


.speed-control {
  display: flex;
  gap: 10px; /* Abstand zwischen den Buttons */
  align-items: center;
}

.speed-btn {
  border-radius: 20px;
  border: 4px solid #000;
  padding: 10px 20px; /* Innenabstand */
  cursor: pointer; /* Zeiger beim Hovern */
  background-color: transparent; /* Standard Hintergrundfarbe */
  transition: background-color 0.3s, color 0.3s; /* Weicher Übergang */
  width: 168.364px;
  height: 90px;
}

.speed-btn.active {
  background-color: #000; /* Hintergrundfarbe für aktive Buttons */
}

.speed-number {
  text-align: center;
  font-size: 45px;
  font-style: normal;
  font-weight: 420;
  line-height: 26.784px;
  color: black; /* Standardfarbe */
  transition: color 0.3s; /* Weicher Übergang */
}

.speed-number.active {
  color: #DEF0FC; /* Textfarbe für aktive Buttons */
}


.fa-solid {
  font-size: 127px;
}


.pagination {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  top: 27.5%;
}

.pagination ul {
  display: flex;
  list-style: none; /* Entfernt die Standard-Punkte */
  padding: 0;
  margin: 0;

}

/* Styling für jedes Pagination-Element */
.pagination ul a {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 5px; /* Abstand zwischen den Buttons */
  text-decoration: none; /* Entfernt den Standard-Link-Stil */
}

.pagination ul a li {
  width: 40px; /* Breite der Buttons */
  height: 40px; /* Höhe der Buttons */
  background-color: transparent; /* Standard-Hintergrund */
  border: 2px solid #757575; /* Randfarbe */
  border-radius: 10px; /* Abgerundete Ecken */
  cursor: pointer; /* Zeigt eine Hand an beim Hover */
  transition: all 0.3s ease; /* Animation für Hover-Effekt */
}


/* Styling für das aktive Element */
.pagination ul a.is-active li {
  background-color: black; /* Aktiver Hintergrund */
  border-color: black; /* Gleiche Farbe wie der Hintergrund */
}


@keyframes normal {
  25% {
    transform: scaleY(1);
  }
  50% {
    transform: scaleY(0.4);
  }
  75% {
    transform: scaleY(0.6);
  }
}

@keyframes loud {
  25% {
    transform: scaleY(1);
  }
  50% {
    transform: scaleY(0.4);
  }
  75% {
    transform: scaleY(1.2);
  }
}


.boxContainer {
  display: flex;
  justify-content: space-between;
  height: 64px;
  --boxSize: 100px;
  --gutter: 4px;
  width: calc((var(--boxSize) + var(--gutter)) * 5);
}

.box {
  transform: scaleY(0.4);
  height: 100%;
  width: var(--boxSize);
  background: #000000;
  animation-duration: 1.2s;
  animation-timing-function: ease-in-out;
  animation-iteration-count: infinite;
  border-radius: 8px;
}

.box1 {
  animation-name: quiet;
}

.box2 {
  animation-name: normal;
}

.box3 {
  animation-name: quiet;
}

.box4 {
  animation-name: loud;
}

.box5 {
  animation-name: quiet;
}

.box6 {
  animation-name: loud;
}

.box7 {
  animation-name: normal;
}

.box8 {
  animation-name: quiet;
}

.box9 {
  animation-name: loud;
}

.box10 {
  animation-name: normal;
}
</style>