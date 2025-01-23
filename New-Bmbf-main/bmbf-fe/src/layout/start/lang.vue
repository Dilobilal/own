<template>
  <div
      class="container d-flex justify-content-center align-items-center"
  >
    <div class=" element d-flex flex-column align-items-center ">
      <div class="row my-5">
        <div class="col-sm-2 d-flex icon">
          <i class="fa-solid fa-earth-americas"></i>
        </div>
        <div class="col-lg sprache">
          <h3>Sprache Auswählen/</h3>
          <h3>Select Your Language</h3>
        </div>
      </div>
      <div class="row">
        <div class="row my-5 texte-allg justify-content-center ">
          <div class=" lg-text">
            <span class="bold-txt">DE</span>
            <br/>
            <span class="normal-txt">Berühre den Bildschirm mit deinen Fingern, um zu navigieren</span>
          </div>
          <div class="lg-text">
            <span class="bold-txt">EN </span>
            <br/>
            <span class="normal-txt">Touch the Screen With your fingers to navigate the menus</span>
          </div>
        </div>
        <div class="d-flex justify-content-center align-items-center text-center o">
          <div class="toggle-switch">
            <input type="radio" id="de" name="language" checked>
            <label for="de" class="toggle-option de"> <span> DE </span> </label>
            <input type="radio" id="en" name="language">
            <label for="en" class="toggle-option en"><span> EN </span></label>
          </div>
        </div>
      </div>
      <div class="pagination p-element mx-5 ">
        <ul>
          <a href="#"><li></li></a>
          <a href="#"><li></li></a>
          <a href="#"><li></li></a>
          <a href="#"><li></li></a>
          <a class="is-active" href="#"><li></li></a>
          <a href="#"><li></li></a>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "lang",
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
  width: 1068px;
  height: 172px;

}

h3 {
  color: #000;
  font-size: 90px;
  font-style: normal;
  font-weight: 800;
  line-height: 95.89%; /* 86.301px */
}

.fa-solid {
  font-size: 96px;
}

.texte-allg {

  gap: 172px;
}

.lg-text {

  margin-top: 385px;
  width: 491px;
  height: 329px;
  flex-shrink: 0;
  text-align: left;
}

.bold-txt {
  color: #000;
  font-size: 45px;
  font-style: normal;
  font-weight: 800;
  line-height: 95.89%; /* 43.15px */
}

.o {
  margin-top: 366px;
}

.normal-txt {
  color: #000;
  font-size: 55px;
  font-style: normal;
  font-weight: 380;
  line-height: 95.89%;
}
/* Grundlegendes Styling */
.toggle-switch {
  display: flex;
  width: 532px;
  height: 153.462px;
  border-radius: 124.477px;
  border: 8.031px solid #000;
  overflow: hidden;
  position: relative;
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

.de
{
  font-size: 66.923px;
  font-style: normal;
  font-weight: 420;
  line-height: 35.85px; /* 53.568% */
}
.en
{
  font-size: 66.923px;
  font-style: normal;
  font-weight: 420;
  line-height: 35.85px; /* 53.568% */
}


.pagination ul{


}
.fa-solid {
  font-size: 127px;
}

/* Grundlegendes Styling für die Pagination */
.pagination {
  display: flex;
  justify-content: center; /* Zentriert die Pagination */
  align-items: center;
  position: relative;
  top: 32.2%;
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