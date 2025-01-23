<template>
  <div
      class="container d-flex justify-content-center align-items-center"
  >
    <div ref="element" class=" element d-flex flex-column align-items-center ">
      <div class="row my-5 icon-txt">
        <div class="col-sm-2 d-flex icon">
          <i class="bi bi-eye"></i>
        </div>
        <div class="col-lg sprache d-flex align-items-center ">
          <h3>Text- und Menüposition</h3>
        </div>
      </div>
      <div class="text">
        <span class="bold-txt">Verschiebe den Strich mit deinem Finger nach oben oder unten auf eine angenehme Sichthöhe. So wirst du später Menüs und Texte sehen.</span>
      </div>
      <div class="arrow-container">
        <div class="arrow up-arrow" @click="onArrowClick('up')">↑</div>
        <div class="dashed-line">
          <div class="center-control" @click="onArrowClick('mitte')">⬤</div>
        </div>
        <div class="arrow down-arrow" @click="onArrowClick('down')">↓</div>
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
  name: "textPosition",
  data() {
    return {
      marginTop: 676,
    };
  },
  methods:
      {
        onArrowClick(direction) {
          const div = this.$refs.element; // Zugriff auf das Element mit ref
          if (direction === "up") {
            this.marginTop = 0// Verhindert negative Werte
          }else if (direction === "down") {
            this.marginTop = 1190; // Erhöht margin-top
          }else if (direction === "mitte")
          {
            this.marginTop = 676;
          }
          div.style.marginTop = `${this.marginTop}px`;
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

.text {
  margin-top: 189px;
  width: 1285px;
  height: 388px;
}

.bold-txt {
  color: #000;
  font-size: 55px;
  font-style: normal;
  font-weight: 420;
  line-height: 120%; /* 66px */
}


.arrow-container {
  display: flex;
  flex-direction: column; /* Elemente vertikal anordnen */
  align-items: center; /* Zentriert die Pfeile und Linie */
  justify-content: space-between; /* Gleichmäßige Abstände zwischen den Elementen */
  height: 500px; /* Höhe des Containers */
  position: relative;
  top: 388px;
}

.arrow {
  font-size: 110px; /* Größe der Pfeile */
  color: #000; /* Farbe der Pfeile */
  cursor: pointer; /* Zeiger beim Hovern */
  user-select: none; /* Verhindert Textauswahl */
}

.dashed-line {
  width: 852px; /* Breite der gestrichelten Linie */
  border-top: 5px dashed #000; /* Linie gestrichelt und schwarz */
  margin: 20px 0; /* Reduzierter Abstand zwischen Linie und Pfeilen */
  position: relative;
}

.center-control {
  position: absolute; /* Absolut in der Linie zentriert */
  top: -37px; /* Vertikale Position in der Linie */
  left: 50%; /* Horizontale Position zentriert */
  transform: translateX(-50%);
  font-size: 90px;
  font-weight: bold;
  color: #000;
  background-color: #fff;
  border: 1px solid #000;
  border-radius: 50%;
  width: 60px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  user-select: none;
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

.de {
  font-size: 66.923px;
  font-style: normal;
  font-weight: 420;
  line-height: 35.85px; /* 53.568% */
}

.en {
  font-size: 66.923px;
  font-style: normal;
  font-weight: 420;
  line-height: 35.85px; /* 53.568% */
}


.pagination ul {


}

/* Grundlegendes Styling für die Pagination */
.pagination {
  display: flex;
  justify-content: center; /* Zentriert die Pagination */
  align-items: center;
  position: relative;
  top: 42%;

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