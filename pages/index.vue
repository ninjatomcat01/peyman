<template>
  <div class="home">
    <div class="enHome mont" v-if="language == 'en'">
      <Header lang="eng" @change="change" />
      <div class="topDiv">
        <h3>Peyman Profile Asia Co</h3>
        <h1>
          Manufacturer of aluminum products with the most advanced equipment
        </h1>
        <button class="effectBtn">
          <img src="/icons/blackCall.svg" class="blackCallIcon" />
          <span>Get In Touch</span>
        </button>
        <div class="scroll d-flex justify-content-end align-items-center">
          <span class="scrollTitle">Scroll Down</span>
          <div class="scrollIcon">
            <span class="circle"></span>
          </div>
        </div>
      </div>
      <div class="whoWeAre d-flex justify-content-between align-items-center">
        <div class="texts">
          <h1>Who We Are?</h1>
          <p>
            Peyman Profile Asia Company started its activity in 2016 with
            research in the field of aluminum industry, monitoring market needs
            and building three halls, and with the passage of time and upgrading
            the complex to seven halls and equipping them with the most advanced
            tools for the production of aluminum products ...
          </p>
          <button class="effectBtn">
            <span>Read More</span>
          </button>
        </div>
        <div class="col animation">
          <Lines myVw="685" myVh="605" />
        </div>
      </div>
      <div class="workSmarter">
        <h2>Work smarter. React faster. Think bigger.</h2>
        <p>
          The goals and future plans of this company are based on the following
          policies :
        </p>
        <div class="d-flex justify-content-between icons">
          <div class="iconsDiv">
            <img src="/icons/smarterIcon1.svg" alt="" />
            <div>Equipping and updating machines</div>
          </div>
          <div class="iconsDiv">
            <img src="/icons/smarterIcon2.svg" alt="" />
            <div>Promotion of technical knowledge</div>
          </div>
          <div class="iconsDiv">
            <img src="/icons/smarterIcon3.svg" alt="" />
            <div>Knowing the market of this industry</div>
          </div>
          <div class="iconsDiv">
            <img src="/icons/smarterIcon4.svg" alt="" />
            <div>New standards of aluminum industry</div>
          </div>
        </div>
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
      <div class="units">
        <div class="unitsHead">
          <h2>Units Of Our Company.</h2>
          <button class="effectBtn"><span>Read More</span></button>
        </div>
        <div class="items d-flex justify-content-around flex-wrap">
          <div
            v-for="item in unitItems"
            :key="item.id"
            class="item"
            :class="{ marginItem: item.id % 2 == 0 }"
            :id="`item${item.id}`"
          >
            <div class="number">0{{ item.id }}.</div>
            <div class="title">{{ item.title }}</div>
            <div class="text">{{ item.text }}</div>
          </div>
        </div>
      </div>
      <div
        class="
          animationImage
          col-12
          d-flex
          justify-content-center
          align-items-center
          px-0
        "
      >
        <img src="/images/animationImage.png" v-show="!video" id="trigger" />
        <img
          src="/images/videoImg.jpg"
          class="col-12 px-0 video"
          v-show="video"
        />
      </div>
      <div class="news">
        <div class="newsHead">
          <h2>News.</h2>
          <p>We share the news related to the aluminum industry with you</p>
          <div class="button effectBtn">
            <span> All News </span>
          </div>
        </div>
        <div class="newsList">
          <div
            class="d-flex justify-content-between new"
            v-for="item in newsItems"
            :key="item.id"
            :id="`new${item.id}`"
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
        </div>
      </div>
      <Footer />
    </div>
    <div class="faHome" v-else>
      <Header lang="fa" @change="change" />
    </div>
    <MouseEffect />
  </div>
</template>

<script>
import gsap from "gsap";
import ScrollTrigger from "gsap/dist/ScrollTrigger";
export default {
  data() {
    return {
      language: "",
      unitItems: [
        {
          id: 1,
          title: "Business unit",
          text: "The mission of this unit is to supply raw materials and machines needed for production lines, including casting, extrusion, powder paint, plating and decorative units...",
        },
        {
          id: 2,
          title: "Sales unit",
          text: "The job description in this unit is to provide the best services in the field of sales, support, consulting, surveys and representation in all cities and centers of domestic ...",
        },
        {
          id: 3,
          title: "Extrusion unit",
          text: "Aluminum extrusion (shaping) is a specific process in which the pre-heated billet enters the mold by hydraulic pressure and exits the mold as extruded products in different shapes...",
        },
        {
          id: 4,
          title: "Powder paint unit",
          text: "Electrostatic paint is a technique of using dry paint to cover a piece, which has been the newest method for painting and covering surfaces in general and industrial applications....",
        },
        {
          id: 5,
          title: "Decorative unit",
          text: "The decorative unit is a system that makes it possible to implement granite wood designs or fantasy patterns on all surfaces....",
        },
        {
          id: 6,
          title: "Plating unit",
          text: "The formation of a thin oxide layer on aluminum parts, which increases the hardness of the corrosion resistance, and changes some of its physical properties,..",
        },
        {
          id: 7,
          title: "Warehouse unit",
          text: "After the packaging and labeling process, the produced products are sorted according to a regular...",
        },
        {
          id: 8,
          title: "Warehouse unit",
          text: "The casting unit of this complex uses a tilting melting furnace and an ingot casting furnace, both of which have a capacity of 12 tons per shape.....",
        },
        {
          id: 9,
          title: "Warehouse unit",
          text: "The casting unit of this complex uses a tilting melting furnace and an ingot casting furnace, both of which have a capacity of 12 tons per shape.....",
        },
      ],
      newsItems: [
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
      ],
      video: false,
    };
  },
  mounted() {
    this.language = this.$store.state.lang;
    setTimeout(() => {
      gsap.registerPlugin(ScrollTrigger);
      let tl = gsap.timeline();
      tl.to("#trigger", {
        scrollTrigger: {
          trigger: "#trigger",
          start: "50% center",
          end: "=+400 center",
          scrub: true,
          // markers: true,
        },
        scale: 3,
        top: 230,
      });
    }, 10);
    window.addEventListener("scroll", () => {
      if (
        document.getElementById("trigger").style.top == "230px" &&
        !this.video
      ) {
        this.video = true;
      } else if (
        document.getElementById("trigger").style.top != "230px" &&
        this.video
      ) {
        this.video = false;
      }
      console.log(document.getElementById("trigger").style.top);
    });
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