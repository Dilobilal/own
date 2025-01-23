<template>
  <div class="main">
      <textArt >


      </textArt>
  </div>
</template>

<script>
import container from "../layout/container.vue";
import Audio from "../layout/start/Audio.vue";
import textPosition from "../layout/start/text_menüPosition.vue";
import alter from "../layout/start/alter.vue";
import lang from "../layout/start/lang.vue";
import textArt from "../layout/start/textArt.vue";
import datenSchutz from "../layout/start/datenSchutz.vue";
import info from "../layout/start/information.vue";
import datenSchutzText from "../layout/start/datenSchutzText.vue";
import willkommen from "../layout/start/willkommen.vue";
import wähleGuid from "../layout/start/wähleGuid.vue";

export default {
  name: "start",
  components: { textArt},
};
</script>

<style scoped>
.main {
  background-color: #D9D9D9;
  height: 3840px;
  width: 2160px;
  transform: scale(0.5); /* Skaliert die Webseite auf 50% */

}
</style>