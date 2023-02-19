<template>
  <div class="units">
    <div class="enUnits mont" v-if="language == 'en'">
      <Header lang="eng" @change="change" />
      <div class="topDiv">
        <h3>Units</h3>
        <h1>Units OF Our Company.</h1>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua Egestas
          purus viverra accumsan in nisl nisi Arcu cursus.
        </p>
      </div>
      <div class="lineDiv">
        <Lines myVw="1920" myVh="360" />
      </div>
      <div class="myUnits">
        <section
          v-for="unit in units"
          :key="unit.id"
          class="d-flex justify-content-between unit align-items-center"
          :id="unit.idName"
          :class="{ whiteBack: unit.id % 2 == 0 }"
        >
          <div>
            <h2>{{ unit.title }}</h2>
            <p>{{ unit.text }}</p>
            <router-link to="/" v-if="unit.more">More ...</router-link>
          </div>
          <img :src="unit.image" alt="" />
        </section>
      </div>
      <div class="unitFooter">
        <Footer lang="en" />
      </div>
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
      units: [
        {
          id: 1,
          idName: "BusinessUnit",
          title: "Business unit .",
          image: "/images/businessUnit.jpg",
          text: "Peyman Profile Asia Company, with the support of its customers' trust and the benefit of high production capacity and excellent quality, having experienced and knowledge-oriented forces, has been able to have a special position in the aluminum industry as a professional and influential group.",
          more: false,
        },
        {
          id: 2,
          idName: "salesUnit",
          title: "Sales Unit .",
          image: "/images/salesUnit.jpg",
          text: "The job description in this unit is to provide the best services in the field of sales, support, consulting, surveys and representation in all cities and centers of domestic provinces and neighboring countries. Being honest with the customer, following the principles of customer orientation and providing a wide range of products in different designs, colors and levels (industrial, construction, exclusive, etc.) according to the customer's needs, it is operating.",
          more: false,
        },
        {
          id: 3,
          idName: "extrusionUnit",
          title: "Extrusion unit .",
          image: "/images/extrusionUnit.jpg",
          text: "Aluminum extrusion (shaping) is a specific process in which the pre-heated billet enters the mold by hydraulic pressure and exits the mold as extruded products in different shapes. Extrusion presses are made in certain sizes and their size is directly related to the size of the billet to be extruded. The extrusion unit of this complex, having three extrusion presses of 1200, 1800 and 2200 tons",
          more: true,
        },
        {
          id: 4,
          idName: "powderPaintUnit",
          title: "Powder paint unit .",
          image: "/images/powderPaintUnit.jpg",
          text: "Electrostatic paint is a technique of using dry paint to cover a piece, which has been the newest method for painting and covering surfaces in general and industrial applications. In this method, by creating a very uniform and high-quality paint coating, it has made the profile strong and resistant. And it makes it more resistant and durable to environmental factors such as heat, cold, humidity, wear, impact, ultraviolet rays of the sun, corrosion, etc. ",
          more: true,
        },
        {
          id: 5,
          idName: "decorativeUnit",
          title: "Decorative unit .",
          image: "/images/decorativeUnit.jpg",
          text: "The decorative unit is a system that makes it possible to implement granite wood designs or fantasy patterns on all surfaces. Undoubtedly, the colors and designs found in nature are very eye-catching and relaxing. In terms of appearance, the wood design decorative coverings are close to real examples of expensive and beautiful woods such as walnut, beech, oak, hazelnut, etc., which, in addition to preserving natural resources, make the appearance of the home environment, ",
          more: true,
        },
        {
          id: 6,
          idName: "platingUnit",
          title: "Plating Unit .",
          image: "/images/platingUnit.jpg",
          text: "The formation of a thin oxide layer on aluminum parts, which increases the hardness of the corrosion resistance, and changes some of its physical properties, is electroplating (anadize means the artificial oxide layer created on the surface of its profile in any weather condition against humidity) And it resists color change. Other benefits of profile plating: improving the appearance and creating a decorative appearance, increasing wear resistance. .",
          more: true,
        },
        {
          id: 7,
          idName: "packagingUnit",
          title: "Packaging & Lable Unit .",
          image: "/images/packagingUnit.jpg",
          text: "After passing the quality control stage, the final product is transferred to the packaging department, labeled and packaged. Peyman Profil Asia has a fully automatic labeling machine that labels the profiles with the company's exclusive logo (PPA and Arall) to prevent any scratches on the profiles.",
          more: false,
        },
        {
          id: 8,
          idName: "warehousUnit",
          title: "Warehous unit .",
          image: "/images/warehousUnit.jpg",
          text: "After packaging and labeling, the manufactured products are classified according to a regular system and stored in the warehouse until the time of shipment and delivery.",
          more: false,
        },
        {
          id: 9,
          idName: "castingUnit",
          title: "Casting Unit .",
          image: "/images/castingUnit.jpg",
          text: "The casting unit of this complex uses a tilting melting furnace and an ingot casting furnace, both of which have a capacity of 12 tons per shape. , is 12 tons per day in alloy groups from 1000 to 7000 and now the vision of the company for casting is to create another tilting furnace with a tonnage of 12 tons per shape and a rotary furnace of 5 tons with horizontal casting.",
          more: false,
        },
      ],
    };
  },
  mounted() {
    this.language = this.$store.state.lang;
    setTimeout(() => {
      gsap.registerPlugin(ScrollTrigger);

      gsap.set(".myUnits", { autoAlpha: 1 });

      var allSections = gsap.utils.toArray("section");
      var allSectionsNotFirst = allSections.slice(1);
      gsap.set(allSectionsNotFirst, { position: "absolute" });

      var dur = 0.5,
        next = 3,
        dur = 1,
        tt = 3000;

      var action = gsap
        .timeline({
          defaults: {
            duration: dur,
            ease: "none",
            stagger: next,
          },
        })
        .to(allSectionsNotFirst, { yPercent: -100 })
        .to({}, { duration: 1 });

      ScrollTrigger.create({
        trigger: ".myUnits",
        start: "top top",
        end: "+=" + tt,
        pin: true,
        animation: action,
        scrub: 0.3,
      });
    }, 10);
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