<template>
  <div class="header">
    <div v-if="lang == 'eng'" class="enHeader d-flex justify-content-between">
      <img src="/images/whiteLogo.png" class="whiteLogo" />
      <div class="d-flex">
        <router-link to="/" :class="{ active: page == 1 }"> Home </router-link>
        <router-link to="/aboutUs" :class="{ active: page == 2 }">
          Who We Are
        </router-link>
        <router-link to="/products" :class="{ active: page == 3 }">
          Products
        </router-link>
        <router-link to="/units" :class="{ active: page == 4 }">
          Units
        </router-link>
        <router-link to="/media" :class="{ active: page == 5 }">
          Media
        </router-link>
        <router-link to="/news" :class="{ active: page == 6 }">
          News
        </router-link>
        <router-link to="/contactUs" :class="{ active: page == 7 }">
          Get In Touch
        </router-link>
        <div class="d-flex">
          <div class="d-flex pointer globalDiv" @click="change">
            <img src="/icons/global.svg" class="globalIcon" />
            <div class="langDiv">
              {{ language.toUpperCase() }}
            </div>
          </div>
          <img src="/icons/search.svg" class="searchIcon" />
        </div>
      </div>
    </div>
    <div v-else class="faHeader d-flex justify-content-between">
      <img src="/images/whiteLogo.png" class="whiteLogo" />
      <div class="d-flex">
        <router-link to="/" :class="{ active: page == 1 }">
          صفحه اصلی
        </router-link>
        <router-link to="/aboutUs" :class="{ active: page == 2 }">
          درباره ی ما
        </router-link>
        <router-link to="/products" :class="{ active: page == 3 }">
          محصولات
        </router-link>
        <router-link to="/units" :class="{ active: page == 4 }">
          واحد های تولیدی
        </router-link>
        <router-link to="/media" :class="{ active: page == 5 }">
          گالری
        </router-link>
        <router-link to="/news" :class="{ active: page == 6 }">
          اخبار
        </router-link>
        <router-link to="/contactUs" :class="{ active: page == 7 }">
          تماس با ما
        </router-link>
      </div>
      <div class="d-flex lastHeadDiv">
        <div class="d-flex">
          <img src="/icons/bag.svg" class="bagIcon" />
          <div class="bagDiv">سفارش</div>
        </div>
        <div class="blueLine"></div>
        <div class="d-flex pointer globalDiv" @click="change">
          <img src="/icons/global.svg" class="globalIcon" />
          <div class="langDiv">
            {{ language.toUpperCase() }}
          </div>
        </div>
        <div class="blueLine"></div>
        <img src="/icons/search.svg" class="searchIcon" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "headerCom",
  props: ["lang"],
  data() {
    return {
      language: "",
      page: 1,
    };
  },
  methods: {
    change() {
      this.$emit("change");
    },
  },
  mounted() {
    this.language = this.$store.state.lang;
    if (this.$route.fullPath == "/") {
      this.page = 1;
    }
  },
};
</script>

<style>
</style>