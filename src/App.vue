<template>
  <div class="flex flex-col w-full">
    <Nav style="margin-bottom: 60px" :data="selectedComponents" />

    <Hero :data="''" :custom="getSectionType('hero')" />

    <div v-for="section in data.sections" :key="section.title" :id="section.id">
      <Custom
        v-if="section.type == 'custom'"
        :custom="getSectionData(section.title)"
        :key="section.title"
        id="updates"
      />

      <Edgeryders
        v-if="section.type == 'edgeryders'"
        :custom="getSectionData(section.title)"
      />
    </div>

    <Terms />
  </div>
</template>

<script>
import config from "@/data/config.json";

import Nav from "@/components/Navigation.vue";
import Hero from "@/components/Hero.vue";
import Custom from "@/components/Custom.vue";
import Edgeryders from "@/components/Edgeryders.vue";
import Terms from "@/components/Terms.vue";

export default {
  name: "home",
  data() {
    return {
      data: config,
      category: null,
      categories: null
    };
  },
  components: {
    Hero,
    Nav,
    Custom,
    Edgeryders,
    Terms
  },
  methods: {
    getSectionData(type) {
      return this.data.sections.filter(section => section.title == type)[0];
    },
    getSectionType(type) {
      return this.data.sections.filter(section => section.type == type)[0];
    }
  },
  computed: {
    selectedComponents() {
      return [
        "ethnographer",
        "edgesense",
        "graphryder",
        "dreams",
        "edgeryders"
      ];
    }
  }
};
</script>
<style lang="scss">
#books {
  width: 100% !important;
}
</style>
