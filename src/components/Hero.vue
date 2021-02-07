<template>
  <div class="hero md:hero-md sensestack">
    <div class="content_wrapper md:content_wrapper-md ">
      <div class="animation_wrapper">
        <Orb />
      </div>
      <div class="hero_info">
        <h1 class="hero_title" v-if="isCustom('title')">{{ custom.title }}</h1>
        <p class="hero_text" v-html="custom.text" v-if="isCustom('text')"></p>
      </div>
    </div>
  </div>
</template>

<script>
import Orb from "@/components/Orb.vue";
export default {
  components: {
    Orb
  },
  methods: {
    getLogo() {
      if (this.data.uploaded_logo !== null) {
        return "https://edgeryders.eu/" + this.data["uploaded_logo"]["url"];
      }
    },
    isCustom(field) {
      var x = field;
      if (this.custom[x]) {
        return true;
      } else {
        return false;
      }
    }
  },
  props: ["data", "custom"]
};
</script>
<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Exo+2:100,200,300,400,500,600,700&display=swap");

.hero.sensestack {
  height: 350px;
  background: black;
}
.content_wrapper {
  display: flex;
  height: 100%;
  align-items: center !important;

  width: 90%;
  justify-content: center;
}
.animation_wrapper {
  display: inline-block;
  width: 30%;
  margin-left: -90px;
  margin-right: 20px;
  height: 100%;
  position: relative;
  top: 0px;
}
.hero_info {
  display: flex;
  margin-left: 0px;
  width: auto;
  text-align: left;
  color: white;
  justify-content: center;
  flex-direction: column;
  align-items: start;
  .hero_title {
    border-bottom: 0.5px solid rgba(255, 255, 255, 0.2);
    padding: 0 0px 15px;
    font-weight: 100;
    font-family: "Exo 2" !important;
    font-size: 35px;
    text-align: left;
  }
  .hero_text {
    font-weight: 200;
    font-size: 20px;
    padding-left: 0;
    font-family: "Exo 2" !important;
  }
}
@media (max-width: 640px) {
  .animation_wrapper {
    display: inline-block;
    width: 30%;
    position: absolute;
    left: 0;
    top: 0px;
    margin-left: 0px;
  }
}
</style>
