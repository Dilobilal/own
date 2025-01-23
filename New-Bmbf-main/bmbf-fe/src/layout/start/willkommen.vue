<template>
  <div class="d-flex align-items-center flex-column start">
    <div class="startBg">
      <div class="anschrift">
        <span>Herzlich Willkommen in der Grube Messel!</span>
      </div>
      <div class="txt-button d-flex">
        <div class="txt">
        <span>
          Möchtest du einen geführten Rundgang durch die Ausstellung oder lieber alles alleine erkunden?
        </span>
        </div>
        <div class="buttons">
          <button class="option-button" @click="selectOption('auf-eigene-faust')">
            <span>Auf eigene Faust</span>
          </button>
          <button
              class="option-button"
              :class="{ active: selectedOption === 'geführter-rundgang' }"
              @click="selectOption('geführter-rundgang')"
          >
            <span>Geführter Rundgang</span>
          </button>
        </div>
      </div>

      <!-- Zusätzliche Frage -->
      <div v-if="selectedOption === 'geführter-rundgang'" class="additional-question">
        <div class="question-text">
          <span>Wie viele Personen?</span>
        </div>
        <div class="guided-tour-options">
          <button
              class="option-button"
              :class="{ active: selectedSubOption === 'solo' }"
              @click="selectSubOption('solo')"
          >
            <span>Solo</span>
          </button>
          <button
              class="option-button"
              :class="{ active: selectedSubOption === '2-4' }"
              @click="selectSubOption('2-4')"
          >
            <span>2-4</span>
          </button>
          <button
              class="option-button"
              :class="{ active: selectedSubOption === '5-10' }"
              @click="selectSubOption('5-10')"
          >
            <span>5-10</span>
          </button>
          <button
              class="option-button"
              :class="{ active: selectedSubOption === '10-oder-mehr' }"
              @click="selectSubOption('10-oder-mehr')"
          >
            <span>10 oder mehr</span>
          </button>
        </div>
      </div>
    </div>
  </div>


</template>

<script>
export default {
  data() {
    return {
      selectedOption: null, // Hauptauswahl (z. B. 'geführter-rundgang')
      selectedSubOption: null, // Unterauswahl (z. B. 'solo', '2-4', etc.)
    };
  },
  methods: {
    selectOption(option) {
      this.selectedOption = option; // Setzt die Hauptauswahl
      this.selectedSubOption = null; // Setzt die Unterauswahl zurück
    },
    selectSubOption(subOption) {
      this.selectedSubOption = subOption; // Setzt die Unterauswahl
    },
  },
};
</script>

<style scoped>

/* Allgemeine Stile */
.start {
  background-color: #DEF0FC;
  height: 3840px;
  width: 2160px;
}

.anschrift {
  width: 1822px;
  height: 1206px;
  margin-top: 200px;
}

.anschrift span {
  color: #000;
  font-size: 255px;
  font-style: normal;
  font-weight: 800;
  line-height: 100%;
  letter-spacing: -5.1px;
}

.txt-button {
  display: flex;
  justify-content: space-between; /* Platz zwischen Text und Buttons */
  align-items: center; /* Vertikale Zentrierung */
  width: 1729px;
  height: 549px;
  margin-top: 50px;
}

.txt {
  width: 776px;
  height: 549px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.txt span {
  color: #000;
  font-size: 55px;
  font-style: normal;
  font-weight: 380;
  line-height: 120%;
}

/* Buttons */
.buttons {
  display: flex;
  flex-direction: column; /* Buttons untereinander */
  gap: 130px; /* Abstand zwischen den Buttons */
  height: 549px;
  justify-content: flex-end;
}

.option-button{
  width: 852px;
  height: 135px;
  border-radius: 30px;
  border: 4px solid #000;
  background-color: transparent;
  font-size: 20px;
  font-weight: bold;
  color: #000;
  cursor: pointer;
  transition: all 0.3s ease;
}

.option-button span{
  color: inherit;
  font-size: 45px;
  font-style: normal;
  font-weight: 380;
  line-height: 26.784px;
}

/* Aktiver Button */
.option-button.active{
  background-color: #000;
  color: #fff;
}



/* Geführter Rundgang Optionen */
.guided-tour-options {
  width: 1730px;
  display: flex;
  align-items: flex-end;
  flex-direction: column; /* Vertikale Anordnung */
  gap: 30px; /* Abstand zwischen den Buttons */
  margin-top: 50px; /* Abstand von den Hauptbuttons */
}

.guided-tour-options .option-button {
  width: 852px;
  height: 100px;
  border-radius: 20px;
  border: 2px solid #000;
  background-color: transparent;
  font-size: 20px;
  font-weight: bold;
  color: #000;
  cursor: pointer;
  transition: all 0.3s ease;
}

.guided-tour-options .option-button span {
  font-size: 45px;
  font-style: normal;
  font-weight: 380;
  line-height: 26.784px;
}

/* Zusätzliche Frage */
.additional-question {
  margin-top: 30px;
  display: flex;
  flex-direction: column;
  gap: 20px; /* Abstand zwischen Text und Optionen */
  align-items: flex-start; /* Linksbündig */
}

.question-text span {
  color: #000;
  font-size: 55px;
  font-style: normal;
  font-weight: 380;
  line-height: 120%;
}


</style>