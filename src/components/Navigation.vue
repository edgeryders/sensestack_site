<template>
  <header>
    <div class="menu md:pr-2">
      <span class="nav-item logo"></span>
      <scrollactive
        class="nav"
        active-class="active"
        :offset="80"
        :duration="800"
        bezier-easing-value=".5,0,.35,1"
      >
        <a
          class="nav-item scrollactive-item"
          :href="'#' + item"
          v-for="item in filtered"
          :key="item"
          >{{ item }}</a
        >
      </scrollactive>
    </div>
  </header>
</template>

<script>
/**
 * Used as main page navigation in templates.
 */
export default {
  name: "Navigation",
  props: ["data"],
  computed: {
    filtered() {
      return this.data.filter(function(el) {
        return el !== "terms" && el !== "hero";
      });
    }
  }
};
</script>

<style lang="scss" scoped>
.menu {
  background-color: rgba(0, 0, 0, 1);
  display: flex;
  position: fixed;
  top: 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1) !important;
  z-index: 11;
  justify-content: space-between;
  width: 100%;
  align-items: center;
}

.nav {
  @apply font-display;
  font-family: "Exo 2";
  font-weight: 200;
  white-space: nowrap;
  overflow-x: scroll;
  width: auto;
  overflow-y: hidden;
  -webkit-overflow-scrolling: touch;
  -ms-overflow-style: -ms-autohiding-scrollbar;
  &::-webkit-scrollbar {
    display: none;
  }
}

.nav-item {
  height: 45px;
  display: inline-flex;
  cursor: pointer;
  padding: 16px 16px 14px;
  text-transform: capitalize;
  align-items: center;
  color: white !important;
  border: none;
  border-left: 1px solid rgba(255, 255, 255, 0.2) !important;
  &:first-child {
    border-left: none !important;
  }
  &.active {
    color: #fff !important;
    background-color: rgba(255, 255, 255, 0.1) !important;
    border-left: 1px solid rgba(255, 255, 255, 0) !important;
    border: none !important;
    border-radius: 5px;
  }
}

.active + .nav-item {
  border-left: 1px solid rgba(255, 255, 255, 0) !important;
}

.logo {
  min-width: 65px;
  height: 60px;
  padding: 0 50px 0 20px;
  border: none;
  background: url("data:image/svg+xml,%3Csvg viewBox='0 0 500 500' version='1' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill='white' d='M0 250a250 250 0 1 1 500 0 250 250 0 0 1-500 0zm250 183V250H67a183 183 0 1 1 183 183z' fill-rule='evenodd'/%3E%3C/svg%3E")
    no-repeat center rgba(0, 0, 0, 0.3);
  background-size: 45%;
  transition: none;
  box-shadow: none;
  left: 0;
  z-index: 99999;
}
</style>
