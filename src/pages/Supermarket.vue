<template>
  <q-page class="flex flex-center background">
    <div class="row">
      <div class="col-9">
        <img
          v-for="fruita in fruites"
          :key="fruita.url"
          :src="fruita.url"
          :alt="fruita.nom"
          @click="beep"
        />
      </div>
      <div class="col-3">
        <span class="counter">{{ comptador }}</span>
      </div>
    </div>
    <audio id="beep">
      <source src="audio/beep2.mp3" type="audio/mpeg" />
      Your browser does not support the audio element.
    </audio>
  </q-page>
</template>

<script>
export default {
  name: "PageIndex",
  data() {
    return {
      comptador: 0,
      fruites: [
        {
          nom: "PLATAN",
          url: "img/banana.jpg",
        },
        {
          nom: "RAIM",
          url: "img/grape.png",
        },
        {
          nom: "TARONJA",
          url: "img/orange.png",
        },
        {
          nom: "POMA",
          url: "img/apple.png",
        },
        {
          nom: "DONUTS",
          url: "img/donut.jpg",
        },
        {
          nom: "KIWI",
          url: "img/kiwi.jpg",
        },
        {
          nom: "LLIMONA",
          url: "img/lemon.jpg",
        },
        {
          nom: "MELICOTÓ",
          url: "img/peach.png",
        },
        {
          nom: "PERA",
          url: "img/pear.jpg",
        },
        {
          nom: "FRESA",
          url: "img/strawberry.jpg",
        },
        {
          nom: "SÍNDRIA",
          url: "img/watermelon.jpg",
        },
      ],
    };
  },
  methods: {
    beep() {
      console.log("hola");
      const audio = document.querySelector("#beep");
      audio.play();
      this.comptador = (this.comptador + 1) % 11;
    },
  },
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  touch-action: manipulation;
}

img {
  background: white;
  width: 200px;
  height: 200px;
  border: 1px solid #000;
  object-fit: cover;
  touch-action: manipulation;
}

.background {
  padding: 10px;
  background: url("~assets/img/background/background11.jpg");
  width: 100%;
  height: 100%;
  display: flex;
  flex-wrap: wrap;
  row-gap: 10px;
  column-gap: 10px;
  touch-action: manipulation;
}

.counter {
  font-size: 25em;
}
</style>
