<template>
  <div class="aboutUs">
    <div class="enAboutUs mont" v-if="language == 'en'">
      <Header lang="eng" @change="change" />
      <div class="topDiv d-flex justify-content-between">
        <div>
          <h2>About Us</h2>
          <h1>Who We Are?</h1>
          <div class="myLines">
            <Lines myVw="550" myVh="110" />
          </div>
        </div>
        <div>
          <h4>History</h4>
          <p>
            In 2016, Peyman Profile Asia Company started its activities with
            research in the field of aluminum industries, monitoring the market
            needs, relying on the scientific and experimental treasures of its
            managers in the field of design and relying on the customer-oriented
            policy and improving the quality of aluminum products, casting
            units, press Extrusion, electrostatic paint, electroplating services
            and decorative paint were put into operation. In 1395, with the use
            of a land area of ​​16000 square meters and dimensions of 6000
            square meters, a casting line was set up using the DC method and
            ingot casting in 1000 alloy. It has increased to 7000, and also a
            1800 ton extrusion press has been added to the company's capacity,
            which was put into operation in 2018.
          </p>
        </div>
      </div>
      <div
        class="capabilities d-flex justify-content-between align-items-center"
      >
        <div>
          <h2>Our Capabilities</h2>
          <ul>
            <li>
              <span>
                Production of all kinds of extruded aluminum sections (special,
                industrial, construction)
              </span>
            </li>
            <li>
              <span>
                Sale of billets, all kinds of alloy ingots and raw materials
                related to the aluminum industry
              </span>
            </li>
            <li>
              <span>
                Production and sale of all kinds of sheets in different
                dimensions and thickness according to customer's order
              </span>
            </li>
            <li>
              <span>
                Designing and manufacturing all kinds of industrial, special
                molds and extrusion orders
              </span>
            </li>
            <li>
              <span>
                DC tilting furnace billet casting (billet size from 5 inches to
                8 inches in alloys 1000 to 7000)
              </span>
            </li>
            <li>
              <span> Ingot casting in alloys 1000 to 7000 </span>
            </li>
          </ul>
        </div>
        <img src="/images/capabilities.jpg" alt="" />
      </div>
      <div class="activities d-flex justify-content-between align-items-center">
        <img src="/images/activities.jpg" alt="" />
        <div>
          <h2>Our Activities</h2>
          <ul>
            <li>
              <span>
                Production of all kinds of exclusive aluminum extrusion
                sections, industrial, construction).
              </span>
            </li>
            <li>
              <span>
                Sale of billets of all kinds of alloy ingots and raw materials
                related to the aluminum industry.
              </span>
            </li>
            <li>
              <span>
                Supplying and selling all kinds of sheets in different sizes and
                thicknesses according to customer's order.
              </span>
            </li>
            <li>
              <span>
                Designing and manufacturing all kinds of industrial, special
                molds and extrusion orders
              </span>
            </li>
            <li>
              <span>
                Casting with tilting furnace by DC method with billet sizes of 7
                and 8 inches in alloys from 1000 to 7000
              </span>
            </li>
            <li>
              <span> Ingot casting in 1000 to 7000 alloys </span>
            </li>
          </ul>
        </div>
      </div>
      <div class="visions">
        <h2>Our Visions</h2>
        <p>
          Peyman Profile Asia Company, with the support of its customers' trust
          and the benefit of high production capacity and excellent quality,
          having experienced and knowledge-oriented forces, has been able to
          have a special position in the aluminum industry as a professional and
          influential group.
        </p>
        <p>
          The goals and future plans of this company are based on the following
          policies :
        </p>
        <div class="items">
          <div class="d-flex justify-content-between">
            <div class="item">
              <img src="/icons/smarterIcon1.svg" alt="" />
              <h3>Equipping and updating machines</h3>
              <p>
                Equipping and updating factory machines with the most advanced
                technology of the day
              </p>
            </div>
            <div class="item item2">
              <img src="/icons/smarterIcon2.svg" alt="" />
              <h3>Promotion of technical knowledge</h3>
              <p>
                Continuous improvement of the technical knowledge of our experts
                and new information
              </p>
            </div>
          </div>
          <div class="d-flex justify-content-between">
            <div class="item">
              <img src="/icons/smarterIcon3.svg" alt="" />
              <h3>Knowing the market of this industry</h3>
              <p>
                Knowing the market of this industry in the international arena
                and providing the best suggestions and producing special
                sections to meet the market's needs
              </p>
            </div>
            <div class="item item2">
              <img src="/icons/smarterIcon4.svg" alt="" />
              <h3>New standards of aluminum industry</h3>
              <p>
                Acquiring new standards of the aluminum industry in management,
                production lines, products and customer interaction
              </p>
            </div>
          </div>
        </div>
      </div>
      <Footer lang="en" />
    </div>
    <div class="faAboutUs irancell" v-else>
      <Header lang="fa" @change="change" />
      <div class="topDiv d-flex justify-content-between">
        <div>
          <h2 class="mont">About Us</h2>
          <h1>درباره ی ما</h1>
          <div class="myLines">
            <Lines myVw="550" myVh="110" />
          </div>
        </div>
        <div>
          <h4>تاریخچه</h4>
          <p>
            شرکت پیمان پروفیل آسیا در سال 1395 با تحقیق در زمینه صنایع
            آلومینیوم، رصد نیازهای بازار، با تکیه بر گنجینه علمی و تجربی مدیران
            خود در زمینه طراحی و با تکیه بر سیاست مشتری مداری و ارتقای سطح کیفی،
            فعالیت خود را آغاز کرد. کیفیت محصولات آلومینیومی، واحدهای ریخته گری،
            پرس اکستروژن، رنگ الکترواستاتیک، خدمات آبکاری و رنگ تزئینی مورد بهره
            برداری قرار گرفت. در سال 1395 با استفاده از زمینی به مساحت 16000 متر
            مربع و ابعاد 6000 متر مربع خط ریخته گری به روش DC و ریخته گری شمش در
            آلیاژ 1000 راه اندازی شد. به 7000 دستگاه افزایش یافته و همچنین یک
            دستگاه پرس اکستروژن 1800 تنی نیز به ظرفیت شرکت اضافه شده است که در
            سال 1397 به بهره برداری رسید.
          </p>
        </div>
      </div>
      <div
        class="capabilities d-flex justify-content-between align-items-center"
      >
        <div>
          <h2>Our Capabilities</h2>
          <ul>
            <li>
              <span>
                Production of all kinds of extruded aluminum sections (special,
                industrial, construction)
              </span>
            </li>
            <li>
              <span>
                Sale of billets, all kinds of alloy ingots and raw materials
                related to the aluminum industry
              </span>
            </li>
            <li>
              <span>
                Production and sale of all kinds of sheets in different
                dimensions and thickness according to customer's order
              </span>
            </li>
            <li>
              <span>
                Designing and manufacturing all kinds of industrial, special
                molds and extrusion orders
              </span>
            </li>
            <li>
              <span>
                DC tilting furnace billet casting (billet size from 5 inches to
                8 inches in alloys 1000 to 7000)
              </span>
            </li>
            <li>
              <span> Ingot casting in alloys 1000 to 7000 </span>
            </li>
          </ul>
        </div>
        <img src="/images/capabilities.jpg" alt="" />
      </div>
      <div class="activities d-flex justify-content-between align-items-center">
        <img src="/images/activities.jpg" alt="" />
        <div>
          <h2>Our Activities</h2>
          <ul>
            <li>
              <span>
                Production of all kinds of exclusive aluminum extrusion
                sections, industrial, construction).
              </span>
            </li>
            <li>
              <span>
                Sale of billets of all kinds of alloy ingots and raw materials
                related to the aluminum industry.
              </span>
            </li>
            <li>
              <span>
                Supplying and selling all kinds of sheets in different sizes and
                thicknesses according to customer's order.
              </span>
            </li>
            <li>
              <span>
                Designing and manufacturing all kinds of industrial, special
                molds and extrusion orders
              </span>
            </li>
            <li>
              <span>
                Casting with tilting furnace by DC method with billet sizes of 7
                and 8 inches in alloys from 1000 to 7000
              </span>
            </li>
            <li>
              <span> Ingot casting in 1000 to 7000 alloys </span>
            </li>
          </ul>
        </div>
      </div>
      <div class="visions">
        <h2>Our Visions</h2>
        <p>
          Peyman Profile Asia Company, with the support of its customers' trust
          and the benefit of high production capacity and excellent quality,
          having experienced and knowledge-oriented forces, has been able to
          have a special position in the aluminum industry as a professional and
          influential group.
        </p>
        <p>
          The goals and future plans of this company are based on the following
          policies :
        </p>
        <div class="items">
          <div class="d-flex justify-content-between">
            <div class="item">
              <img src="/icons/smarterIcon1.svg" alt="" />
              <h3>Equipping and updating machines</h3>
              <p>
                Equipping and updating factory machines with the most advanced
                technology of the day
              </p>
            </div>
            <div class="item item2">
              <img src="/icons/smarterIcon2.svg" alt="" />
              <h3>Promotion of technical knowledge</h3>
              <p>
                Continuous improvement of the technical knowledge of our experts
                and new information
              </p>
            </div>
          </div>
          <div class="d-flex justify-content-between">
            <div class="item">
              <img src="/icons/smarterIcon3.svg" alt="" />
              <h3>Knowing the market of this industry</h3>
              <p>
                Knowing the market of this industry in the international arena
                and providing the best suggestions and producing special
                sections to meet the market's needs
              </p>
            </div>
            <div class="item item2">
              <img src="/icons/smarterIcon4.svg" alt="" />
              <h3>New standards of aluminum industry</h3>
              <p>
                Acquiring new standards of the aluminum industry in management,
                production lines, products and customer interaction
              </p>
            </div>
          </div>
        </div>
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