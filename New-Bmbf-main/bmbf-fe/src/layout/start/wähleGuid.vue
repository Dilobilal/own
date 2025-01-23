<template>
  <div class="d-flex align-items-center flex-column start">
    <div class="startBg">
      <div class="anschrift">
        <span>Wähle einen Guide!</span>
      </div>
      <div class="guides-container">
        <!-- Guide 1 -->
        <div class="guide" @click="selectGuide(1)">
          <div class="circle" :class="{ active: selectedGuide === 1 }"></div>
          <p :class="{ faded: selectedGuide !== 1 }">
            Guide A ist eine wunderbare Heiterkeit hat meine ganze Seele eingenommen, gleich den süßen Frühlingsmorgen, die ich mit ganzem.
          </p>
        </div>
        <!-- Guide 2 -->
        <div class="guide" @click="selectGuide(2)">
          <div class="circle" :class="{ active: selectedGuide === 2 }"></div>
          <p :class="{ faded: selectedGuide !== 2 }">
            Guide A ist eine wunderbare Heiterkeit hat meine ganze Seele eingenommen, gleich den süßen Frühlingsmorgen, die ich mit ganzem.
          </p>
        </div>
        <!-- Guide 3 -->
        <div class="guide" @click="selectGuide(3)">
          <div class="circle" :class="{ active: selectedGuide === 3 }"></div>
          <p :class="{ faded: selectedGuide !== 3 }">
            Wunderbare Heiterkeit hat meine ganze Seele eingenommen, gleich den süßen Frühlingsmorgen, die ich mit ganzem.
          </p>
        </div>
      </div>
      <button class="btn btn-next position-fixed end-0 top-50 a">
        <span>Die Tour starten</span>
        <i class="fa-solid fa-arrow-right"></i>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedGuide: null,
    };
  },
  methods: {
    selectGuide(index) {
      this.selectedGuide = index;
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
  height: auto;
  margin-top: 200px;
  margin-bottom: 50px;
}

.anschrift span {
  color: #000;
  font-size: 255px;
  font-style: normal;
  font-weight: 800;
  line-height: 100%;
  letter-spacing: -5.1px;
}

.guides-container {

  display: flex;
  justify-content: center;
  gap: 90px; /* Abstand zwischen den Guides */
}

.guide {
  display: flex;
  flex-direction: column; /* Elemente vertikal anordnen */
  align-items: center;
  text-align: left;
  width: 546px;
}

.circle {
  width: 546px;
  height: 546px;
  border-radius: 50%; /* Perfekter Kreis */
  background: #D9D9D9; /* Standard-Hintergrundfarbe */
  border: 5px solid transparent; /* Transparenter Rand */
  transition: all 0.3s ease; /* Weicher Übergang */
}

.circle.active {
  border-color: #0854A1; /* Blau für aktiven Zustand */
}
.circle:hover {
  border-color: #000; /* Schwarzer Rand beim Hovern */
}

.guide p {
  color: #000;
  font-size: 45px;
  font-style: normal;
  font-weight: 420;
  line-height: 150%; /* 67.5px */
  margin-top: 80px;
  transition: all 0.3s ease; /* Weicher Übergang */
}

.guide p.faded {
  color: rgba(0, 0, 0, 0.4); /* Leichterer Text für nicht aktiven Zustand */
}

.start-tour-button button {
  background-color: #00C853;
  border: none;
  border-radius: 30px;
  color: #fff;
  font-size: 40px;
  font-weight: bold;
  padding: 20px 60px;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 10px;
  transition: all 0.3s ease;
}

.start-tour-button button:hover {
  background-color: #009624; /* Dunkleres Grün beim Hovern */
}

.start-tour-button .arrow {
  font-size: 50px;
}
.btn-next {
  margin-top: 280px;
  border-radius: 377px 0px 0px 377px;
  background-color: #4be381;
  width: 1700px;
  height: 264.21px;
  display: flex;
  align-items: center;
  justify-content: space-between; /* Platz zwischen Text und Pfeil */
  padding: 0 50px; /* Innenabstand links und rechts */
}

.a i {
  font-size: 127px;
  margin-left: auto; /* Verschiebt den Pfeil ganz nach rechts */
}

.a span {
  color: #000;
  font-size: 90px;
  font-style: normal;
  font-weight: 380;
  line-height: 95.89%;
  padding-left: 450px;
}
</style>