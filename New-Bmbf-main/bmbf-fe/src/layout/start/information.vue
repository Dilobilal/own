<template>
  <div
      class="container d-flex justify-content-center align-items-center"
  >
    <div ref="element" class=" element d-flex flex-column align-items-center ">
      <div class="row my-5 icon-txt">

        <div class="col-lg sprache d-flex align-items-center ">
          <h3>Informationen<br>
            zum Projekt!</h3>
        </div>
      </div>
      <div class="txt">
        <span> Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. </span>
      </div>

      <div class="threeelement">
        <div class="image-container">
          <img src="@/assets/messel.png" class="image">
          <img src="@/assets/Vector.png" class="image">
          <img src="@/assets/logo2.png" class="image2">
        </div>
      </div>
      <button class="x-button"></button>
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
  left: 260px;
}


h3 {
  color: #000;
  font-size: 90px;
  font-style: normal;
  font-weight: 800;
  line-height: 95.89%; /* 86.301px */
}

.threeelement
  {
  display: flex;
  width: 100%;
  margin-top: 175px;
  height: 150px;
  padding-left: 280px;
  }

.image-container {
  display: flex;

  gap: 60px; /* Fügt 20px Abstand zwischen den Bildern hinzu */
}

.image2 {
  width: 264.659px;
  height: 246.955px;
  flex-shrink: 0;
}
.icon-txt {
  width: 100%;

}

.x-button {
  position: relative;
  top: 500px;
  width: 80%;
  height: 100px;
  background: none; /* Kein Hintergrund */
  border: none; /* Keine Rahmenlinie */
  cursor: pointer; /* Zeiger beim Hovern */
  outline: none; /* Entfernt den Fokusrahmen */
  display: flex;
  justify-content: flex-end; /* Zentriert die Linien horizontal */
}

.x-button::before,
.x-button::after {
  content: ''; /* Pseudo-Elemente für die Linien */
  position: absolute;
  width: 4px; /* Breite der Linien */
  height: 100%; /* Höhe der Linien */
  background-color: black; /* Farbe der Linien */
  transform-origin: center;
}

.x-button::before {
  transform: rotate(45deg); /* Erste Linie */
}

.x-button::after {
  transform: rotate(-45deg); /* Zweite Linie */
}
.txt {
  width: 1153px;
  height: 1074px;
  margin-top: 80px;
}

.txt span {
  color: #000;
  font-size: 55px;
  font-style: normal;
  font-weight: 420;
  line-height: normal;
}



.green-space span {

  color: #000;
  font-size: 90px;
  font-style: normal;
  font-weight: 380;
  line-height: 95.89%; /* 86.301px */
}

.green-space button {
  background: none; /* Entfernt den Hintergrund */
  border: none; /* Entfernt die Umrandung */
  color: transparent; /* Schrift unsichtbar machen */
}




.info-button span {
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
  top: 22.0%;

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