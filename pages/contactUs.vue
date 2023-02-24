<template>
  <div class="contactUs">
    <div class="enContactUs mont" v-if="language == 'en'">
      <Header lang="eng" @change="change" />
      <div class="topDiv d-flex">
        <div>
          <h3>Contact Us</h3>
          <h1>Get In Touch.</h1>

          <Lines2 myVh="477" myVw="570" />
        </div>
        <div class="informations">
          <div class="bordered d-flex align-items-center">
            <img src="/icons/location.svg" alt="" />
            <h2>Address</h2>
          </div>
          <p>
            the end of 2 Development Street , 4 Hemet Street ,Qutb Industrial
            Town,<span> Arak, IRAN </span>
          </p>
          <div class="bordered d-flex align-items-center marginT">
            <img src="/icons/calling.svg" alt="" />
            <h2>Phone</h2>
          </div>
          <p>+98 86 34135393</p>
          <p>+98 918 161 3624</p>
          <div class="bordered d-flex align-items-center marginT">
            <img src="/icons/sms.svg" alt="" />
            <h2>E-mail</h2>
          </div>
          <p>Info@peymanprofile.com</p>
          <div class="bordered d-flex align-items-center marginT">
            <img src="/icons/heart.svg" alt="" />
            <h2>Follow Us</h2>
          </div>
          <div class="d-flex socials">
            <div class="whiteCircle">
              <img src="/icons/twitter.svg" alt="" />
            </div>
            <div class="whiteCircle">
              <img src="/icons/instagram.svg" alt="" />
            </div>
            <div class="whiteCircle"><img src="/icons/in.svg" alt="" /></div>
          </div>
        </div>
      </div>
      <div class="conversation d-flex justify-content-between">
        <form action="#">
          <h2>Start a Conversation</h2>
          <p>
            Let us know your questions and we'll get back to you as soon as
            possible.
          </p>
          <div class="d-flex justify-content-between">
            <input type="text" placeholder="Name" />
            <input type="email" placeholder="Email *" />
          </div>
          <textarea placeholder="Message *" rows="3"></textarea>
          <el-upload
            class="upload-demo"
            drag
            action="https://jsonplaceholder.typicode.com/posts/"
            :on-preview="handlePreview"
            :on-remove="handleRemove"
            :file-list="fileList"
            multiple
          >
            <div class="el-upload__text">Drop file here or CLICK TO UPLOAD</div>
          </el-upload>
          <div class="size">Attachment cannot exceed <span> 5 MB </span></div>
          <button type="submit" class="effectBtn">
            <span> SEND </span>
          </button>
        </form>

        <Lines myVh="550" myVw="579" />
      </div>
      <Footer lang="en" />
    </div>
    <div class="faContactUs irancell" v-else>
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