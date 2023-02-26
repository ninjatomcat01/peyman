<template>
  <div class="blogs">
    <div class="enBlogs mont" v-if="language == 'en'">
      <Header lang="eng" @change="change" />
      <div class="topDiv">
        <h3>products</h3>
        <h1>Product Of Our Company.</h1>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua Egestas
          purus viverra accumsan in nisl nisi Arcu cursus.
        </p>
      </div>
      <div class="lineDiv">
        <Lines myVw="1920" myVh="360" />
      </div>
      <div
        class="homeProduct1 d-flex align-items-center justify-content-between"
      >
        <div class="texts">
          <h2>Exclusive products<span>.</span></h2>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna
          </p>
          <button class="effectBtn">
            <span> More Info </span>
          </button>
        </div>
        <img src="/images/homeProduct1.png" alt="" />
      </div>
      <div
        class="homeProduct2 d-flex align-items-center justify-content-between"
      >
        <div class="texts">
          <h2>General products<span>.</span></h2>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna
          </p>
          <button class="effectBtn">
            <span> More Info </span>
          </button>
        </div>
        <img src="/images/homeProduct2.png" alt="" />
      </div>
      <div
        class="homeProduct3 d-flex align-items-center justify-content-between"
      >
        <div class="texts">
          <h2>Industrial products<span>.</span></h2>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna
          </p>
          <button class="effectBtn">
            <span> More Info </span>
          </button>
        </div>
        <img src="/images/homeProduct3.png" alt="" />
      </div>
      <div
        class="homeProduct4 d-flex align-items-center justify-content-between"
      >
        <div class="texts">
          <h2>Ingots & billets<span>.</span></h2>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna
          </p>
          <button class="effectBtn">
            <span> More Info </span>
          </button>
        </div>
        <img src="/images/homeProduct4.png" alt="" />
      </div>
      <Footer lang="en" />
    </div>
    <div class="faBlogs irancell" v-else>
      <Header lang="fa" @change="change" />
      <div class="topDiv">
        <h3 class="mont">Blog</h3>
        <h1>همه چیز درباره ی آلومینیوم</h1>
        <p>
          لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده
          از طراحان گرافیک است چاپگرها و متون بلکه روزنامه و مجله در ستون و
          سطرآنچنان که لازم است و برای شرایط فعلی تکنولوژی مورد نیاز.
        </p>
      </div>
      <div class="scroll d-flex justify-content-end align-items-center">
        <div class="scrollIcon">
          <span class="scrollCircle"></span>
        </div>
        <span class="scrollTitle">Scroll Down</span>
      </div>
      <div class="lineDiv">
        <Lines myVw="1920" myVh="360" />
      </div>

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