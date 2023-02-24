<template>
  <div class="blogs">
    <div class="enBlogs mont" v-if="language == 'en'">
      <Header lang="eng" @change="change" />
      <div class="topDiv">
        <h3>Blog</h3>
        <h1>Every Things About Aluminium.</h1>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua Egestas
          purus viverra accumsan in nisl nisi Arcu cursus.
        </p>
      </div>
      <div class="lineDiv">
        <Lines myVw="1920" myVh="360" />
      </div>
      <div class="blogList">
        <div
          class="d-flex justify-content-between blog"
          v-for="item in blogItems"
          :key="item.id"
          :id="`blog${item.id}`"
        >
          <img :src="item.image" alt="" />
          <div class="d-flex flex-column justify-content-between">
            <div class="titleAndText">
              <h3 class="title">{{ item.title }}</h3>
              <p class="text">{{ item.text }}</p>
            </div>
            <div class="number">0{{ item.id }}.</div>
          </div>
        </div>
        <div
          class="pagination d-flex align-items-center justify-content-center"
        >
          <span
            class="num"
            @click="pagination = 1"
            :class="{ active: pagination == 1 }"
            >01</span
          >
          <span class="whiteLine"></span>
          <span
            class="num"
            @click="pagination = 2"
            :class="{ active: pagination == 2 }"
            >02</span
          >
          <span
            class="num"
            @click="pagination = 3"
            :class="{ active: pagination == 3 }"
            >03</span
          >
          <span
            class="num"
            @click="pagination = 4"
            :class="{ active: pagination == 4 }"
            >04</span
          >
        </div>
      </div>
      <Footer lang="en" />
    </div>
    <div class="faBlogs irancell" v-else>
      <Header lang="fa" @change="change" />

      <Footer lang="fa" />
    </div>
    <MouseEffect />
  </div>
</template>
  
  <script>
export default {
  data() {
    return {
      language: "",
      pagination: 1,
      blogItems: [
        {
          id: 1,
          image: "/images/homeNew1.jpg",
          title: "Lorem ipsum dolor sit",
          text: `Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
                ut labore et dolore magna aliqua Egestas purus viverra accumsan in nisl nisi Arcu cursus
                vitae congue mauris rhoncus aenean vel elit scelerisque ...`,
        },
        {
          id: 2,
          image: "/images/homeNew2.jpg",
          title: "Lorem ipsum dolor sit",
          text: `Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
                ut labore et dolore magna aliqua Egestas purus viverra accumsan in nisl nisi Arcu cursus
                vitae congue mauris rhoncus aenean vel elit scelerisque ...`,
        },
        {
          id: 3,
          image: "/images/homeNew3.jpg",
          title: "Lorem ipsum dolor sit",
          text: `Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
                ut labore et dolore magna aliqua Egestas purus viverra accumsan in nisl nisi Arcu cursus
                vitae congue mauris rhoncus aenean vel elit scelerisque ...`,
        },
        {
          id: 4,
          image: "/images/blog4.jpg",
          title: "Lorem ipsum dolor sit",
          text: `Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
                ut labore et dolore magna aliqua Egestas purus viverra accumsan in nisl nisi Arcu cursus
                vitae congue mauris rhoncus aenean vel elit scelerisque ...`,
        },
        {
          id: 5,
          image: "/images/blog5.jpg",
          title: "Lorem ipsum dolor sit",
          text: `Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
                ut labore et dolore magna aliqua Egestas purus viverra accumsan in nisl nisi Arcu cursus
                vitae congue mauris rhoncus aenean vel elit scelerisque ...`,
        },
      ],
    };
  },
  mounted() {
    this.language = this.$store.state.lang;
  },
  methods: {
    change() {
      this.$store.commit("change");
    },
  },
  watch: {
    "$store.state.lang"() {
      this.language = this.$store.state.lang;
    },
  },
};
</script>
  
  <style>
</style>