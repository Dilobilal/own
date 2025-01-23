<template>
  <div
      class="container d-flex justify-content-center align-items-center"
  >
    <div ref="element" class=" element d-flex flex-column align-items-center ">
      <div class="row my-5 icon-txt">
        <div class="col-sm-2 d-flex icon">
          <i class="bi bi-check-lg"></i>
        </div>
        <div class="col-lg sprache d-flex align-items-center ">
          <h3>Fertig!</h3>
        </div>
      </div>
      <div class="txt">
          <span> Akzeptiere unsere Datenschutz-einstellungen und<br> los geht es!  </span>
      </div>
      <div class="space">
      <div class="green-space">
        <button>
        <span>Annehmen</span>
        </button>
      </div>
      </div>
      <div class="button-container">
        <button class="info-button">
          <span class="txt1">Weitere Informationen</span>
          <span class="arrow">→</span>
        </button>
        <button class="info-button">
          <span class="txt1">Datenschutzrichtlinie</span>
          <span class="arrow">→</span>
        </button>
      </div>
      <div class="pagination p-element mx-5 ">
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
export default {
  name: "textArt",
  data() {
    return {
      marginTop: 676,
      selectedBox: null,
    };
  },
  methods:
      {
        selectBox(index) {
          this.selectedBox = index; // Setzt den ausgewählten Index
        },
      },
};
</script>
<style scoped>


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

.bi {
  font-size: 120px;

}

.icon-txt {
  width: 100%;
}

.icon {
  display: flex;
  justify-content: flex-end;
  width: 410px;
}

.txt
{
  width: 900px;
  height: 526px;
  margin-top: 80px;
}
.txt span
{
  color: #000;
  font-size: 90px;
  font-style: normal;
  font-weight: 380;
  line-height: 95.89%;
}


.green-space
{
  border-radius: 377px 0px 0px 377px;
  background-color: #4BE381;
  width: 1450px;
  height: 264.21px;
  margin-top: 360.9px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: 290px;
}
.green-space span
{

  color: #000;
  font-size: 90px;
  font-style: normal;
  font-weight: 380;
  line-height: 95.89%; /* 86.301px */
}

.green-space button
{
  background: none; /* Entfernt den Hintergrund */
  border: none; /* Entfernt die Umrandung */
  color: transparent; /* Schrift unsichtbar machen */
}


.button-container {
  position: relative;
  top: 263px;
  display: flex;
  flex-direction: column; /* Ordnet die Buttons vertikal an */
  gap: 20px; /* Abstand zwischen den Buttons */
  align-items: center; /* Zentriert die Buttons horizontal */
}

.info-button {
  display: flex;
  align-items: center;
  justify-content: space-between; /* Platz zwischen Text und Pfeil */
  width: 805px;
  height: 124px;
  border-radius: 30px;
  border: 4px solid #000;
  background: transparent; /* Kein Hintergrund */
  font-size: 16px; /* Textgröße */
  font-weight: bold;
  color: #000; /* Schwarzer Text */
  padding: 0 20px; /* Innenabstand links und rechts */
  cursor: pointer; /* Zeiger beim Hovern */
  transition: all 0.3s ease; /* Weicher Übergang bei Hover */
}
.info-button span
{
  color: #000;
  font-size: 55px;
  font-style: normal;
  font-weight: 380;
  line-height: 26.784px; /* 48.698% */

}


.info-button .arrow {
  font-weight: bold;
  margin-left: 10px; /* Abstand zwischen Text und Pfeil */
}


/* Verstecken der Radio-Buttons */
.toggle-switch input[type="radio"] {
  display: none;
}

/* Styling für die Label-Optionen */
.toggle-option {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 20px;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.3s ease;
  color: black;
  background-color: white;
}

/* Wenn DE aktiviert ist */
input#de:checked + label[for="de"] {
  color: white;
  background-color: black;
}

/* Wenn EN aktiviert ist */
input#en:checked + label[for="en"] {
  color: white;
  background-color: black;
}

/* Um sicherzustellen, dass die inaktiven Elemente korrekt bleiben */
input#de:checked + label[for="de"] ~ label[for="en"] {
  color: black;
  background-color: white;
}

input#en:checked + label[for="en"] ~ label[for="de"] {
  color: black;
  background-color: white;
}



/* Grundlegendes Styling für die Pagination */
.pagination {
  display: flex;
  justify-content: center; /* Zentriert die Pagination */
  align-items: center;
  position: relative;
  top: 25.1%;

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
</style>