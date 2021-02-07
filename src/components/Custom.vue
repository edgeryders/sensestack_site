<template>
  <div class="section md:section-md" id="about">
    <h1 class="section_title" :id="custom.id" v-if="custom.title">
      {{ custom.title }}
    </h1>
    <div
      class="wrapper md:wrapper-md"
      :class="{ reverse: custom.text.position == 'left' }"
    >
      <div
        v-if="custom.image.url"
        class="section_image md:section_image-md"
        :style="'max-width: ' + custom.image.width + 'px !important'"
      >
        <img class="w-full" :src="getAsset(custom.image.url)" />
      </div>

      <div v-if="custom.video.src" class="section_video">
        <video controls class="rounded-lg overflow-hidden">
          <source :src="getAsset(custom.video.src)" type="video/mp4" />

          Sorry, your browser doesn't support embedded videos.
        </video>
      </div>

      <div v-if="custom.video.youtube" class="section_video">
        <iframe
          width="560"
          height="315"
          :src="'https://www.youtube.com/embed/' + custom.video.youtube"
          frameborder="0"
          allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
      </div>

      <div
        class="w-full section_text md:pt-4"
        v-html="custom.text.content"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    getAsset(file) {
      return require("@/assets/" + file);
    }
  },
  mounted() {
    var file = this.getAsset("edgeryders_group.jpg");
    window.console.log(file);
  },
  props: ["custom"]
};
</script>
<style lang="scss" scoped>
.section_video {
  flex-basis: 350px !important;
  flex-shrink: 0;
  border: none !important;

  margin-top: 10px;
  iframe {
    width: 100%;
  }
}
p {
  &.highlight {
    font-size: 25px;
    font-weight: 400;
    padding-right: 30%;
    line-height: 37px;
    margin: 15px 0 20px;
  }
}
.section_text {
  border: none !important;
  padding-left: 0 !important;
  /deep/ p {
    &.highlight {
      font-size: 25px !important;
      font-weight: 400 !important;
      padding-right: 30% !important;
      line-height: 37px !important;
      margin: 15px 0 20px !important;
    }
  }
}
.section,
.section-md {
  padding-bottom: 0 !important;
}
.section_title {
  font-family: "Exo 2";
  margin: 0px 0 20px;
  font-weight: 400;
  padding-bottom: 20px;
  padding-left: 75px;
  background-size: 50px !important;
  &#dreams {
    margin: 0px 0 10px !important;
    padding-bottom: 15px;
    padding-left: 0px;
  }
  &#edgesense {
    background: url("data:image/svg+xml,%3Csvg width='124' height='122' xmlns='http://www.w3.org/2000/svg'%3E%3Cg transform='translate(.7)' fill='none' fill-rule='evenodd'%3E%3Crect fill='%23FF8400' width='123' height='122' rx='6'/%3E%3Cpath d='M42 55.6c-.4 1.3-1.9 1.9-3.1 1.4-1.3-.6-1.9-2-1.4-3.3A26.2 26.2 0 0148 41.4c1.1-.7 2.6-.4 3.4.8.7 1.1.3 2.7-.8 3.4a21.2 21.2 0 00-8.4 10zm22.7 29.2c1.4-.2 2.6.7 2.9 2 .2 1.4-.7 2.7-2 2.9a25.5 25.5 0 01-16.7-3 2.5 2.5 0 01-1-3.4 2.5 2.5 0 013.4-1 20.6 20.6 0 0013.4 2.5zM78 49.6c-.9-1-.7-2.6.4-3.5 1-.8 2.6-.6 3.5.5a26.3 26.3 0 015.4 15c0 1.4-1 2.5-2.3 2.6-1.4 0-2.5-1-2.6-2.4A21.4 21.4 0 0078 49.6z' fill='%23FFF' fill-rule='nonzero'/%3E%3Cpath d='M70.5 39.8c0-5.5-4.4-10-9.8-10a9.9 9.9 0 00-9.8 10c0 5.5 4.4 10 9.8 10s9.8-4.5 9.8-10zm4.9 0c0 8.2-6.6 14.8-14.7 14.8C52.5 54.6 46 48 46 39.8 46 31.6 52.5 25 60.7 25c8 0 14.7 6.6 14.7 14.8zm16 34.5c0-5.4-4.3-9.9-9.8-9.9a9.9 9.9 0 00-9.8 10c0 5.4 4.4 9.9 9.8 9.9 5.5 0 9.8-4.5 9.8-10zm5 0a14.8 14.8 0 11-29.4 0c0-8.1 6.5-14.8 14.6-14.8 8.2 0 14.7 6.7 14.7 14.8zm-45.6.9c0-5.5-4.4-10-9.8-10a9.9 9.9 0 00-9.8 10c0 5.5 4.4 10 9.8 10s9.8-4.5 9.8-10zm5 0a14.8 14.8 0 11-29.4 0c0-8.2 6.5-14.8 14.6-14.8S55.7 67 55.7 75.2z' fill='%23FFF' fill-rule='nonzero'/%3E%3C/g%3E%3C/svg%3E%0A")
      no-repeat 10px 0px;
  }
  &#graphryder {
    background: url("data:image/svg+xml,%3Csvg width='124' height='122' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Crect fill='%2300D88B' x='.7' width='123' height='122' rx='5'/%3E%3Cpath d='M92.5 74.6a6.4 6.4 0 00-5.3 4L68.8 76v-1.7A14 14 0 0065 66l16-19a7.6 7.6 0 009.5-1.9 7.6 7.6 0 10-12-9.6 7.6 7.6 0 000 9.5l-16 18.8a14.1 14.1 0 00-13.9-1l-8.2-13a9 9 0 10-13-12.3 9 9 0 0010.2 14l8.2 13A14.2 14.2 0 0040.5 77l.6 3.2a14.1 14.1 0 0024.6 4.6c1.3-1.7 2.2-3.5 2.7-5.4l18.4 2.5a6.4 6.4 0 007 5.6 6.4 6.4 0 10-1.3-12.8zm-61.8-27a5.7 5.7 0 117.2-8.8 5.7 5.7 0 11-7.2 8.8zm50.5-9.9a4.3 4.3 0 016-.6 4.3 4.3 0 01.7 6 4.5 4.5 0 01-6.1.7 4.3 4.3 0 01-.6-6.1zm-18 44.9a10.8 10.8 0 01-15.4 1.6 10.9 10.9 0 1113.7-17 10.9 10.9 0 011.6 15.4zm32.4.4a3.2 3.2 0 01-4.4.4 3.1 3.1 0 114-4.8c1.3 1 1.5 3 .4 4.4z' fill='%23FFF' fill-rule='nonzero' stroke='%23FFF' stroke-width='2'/%3E%3C/g%3E%3C/svg%3E%0A")
      no-repeat 10px 0px;
  }
  &#ethnographer {
    background: url("data:image/svg+xml,%3Csvg width='124' height='122' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Crect fill='%2300B7EC' x='.7' width='123' height='122' rx='5'/%3E%3Cpath d='M33 82.8V62a30 30 0 1130 30H42.2a9.2 9.2 0 01-9.2-9.2zM63 87a25 25 0 100-50 25 25 0 000 50zm.5-13a11.5 11.5 0 110-23 11.5 11.5 0 010 23zm-.5-5a7 7 0 100-14 7 7 0 000 14z' fill='%23FFF' fill-rule='nonzero'/%3E%3C/g%3E%3C/svg%3E%0A")
      no-repeat 10px 0px;
  }
}
.section_text {
  padding-top: 0 !important;
  font-family: "Exo 2";
  font-weight: 200;
  line-height: 30px;
  border: none !important;
  /deep/ a {
    font-weight: 400;
    text-decoration: underline;
  }
  /deep/ b {
    font-weight: 400 !important;
  }
  /deep/ h3 {
    font-weight: bold;
    font-size: 20px;
  }
  /deep/ p {
    margin: 10px 0;
  }
  /deep/ ul {
    background: rgba(0, 0, 0, 0.03);
    padding: 20px 20px 20px 35px;
    border-left: 1px solid rgba(0, 0, 0, 0.03);
    li {
      list-style: disc;
      font-size: 16px;
      margin: 0;
      padding: 0;
    }
  }
}
.section_image {
  border: none !important;

  padding-right: 10px;
}
@media (max-width: 640px) {
  .section_image {
    width: 60px !important;
    margin: 0 !important;
  }
  .section_title {
    font-size: 22px;
    background-size: 40px !important;
    background-position: 0 0 !important;
    padding-left: 53px !important;
    padding-bottom: 20px !important;
    &#dreams {
      padding-left: 0px !important;
    }
  }
  .section_video {
    height: auto !important;
    margin: 0 0 10px !important;
    flex-basis: auto !important;
    video {
      margin: 0 !important;
      width: 100% !important;
    }
  }
  .section_text {
    /deep/ p {
      &.highlight {
        padding-right: 0 !important;
        font-size: 20px !important;
        line-height: 30px !important;
      }
    }
  }
  p {
    &.highlight {
      padding-right: 0 !important;
      font-size: 20px !important;
      line-height: 30px !important;
    }
  }
}
</style>
