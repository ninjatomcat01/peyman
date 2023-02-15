<template>
  <div @mouseleave="mouseOut">
    <div class="circles" @mouseenter="mouseEnter">
      <div
        class="circleRow d-flex justify-content-between"
        v-for="i in myRow"
        :key="i"
      >
        <span class="circle" v-for="j in myCol" :key="j"></span>
      </div>
    </div>
    <div class="lines" @mouseleave="mouseOut" @mousemove="mouseMove"></div>
  </div>
</template>

<script>
export default {
  props: ["col", "row"],
  data() {
    return {
      mouse: {
        x: 0,
        y: 0,
      },
      requestId: null,
      lines: [],
      vw: 0,
      vh: 0,
      width: 13,
      height: 3,
      myCol: 0,
      myRow: 0,
    };
  },
  mounted() {
    const circle = document.getElementsByClassName("circle");
    this.myCol = parseInt(this.col);
    this.myRow = parseInt(this.row);
    setTimeout(() => {
      for (let i = 0; i < circle.length; i++) {
        const random = Math.floor(Math.random() * 11);
        if (random > 5) {
          circle[i].className = "circle grayCircle";
        } else {
          circle[i].className = "circle whitCircle";
        }
      }
      this.changeColor;
      this.vw = document.getElementsByClassName("circles")[0].clientWidth;
      this.vh = document.getElementsByClassName("circles")[0].clientHeight;

      for (var y = -10; y <= this.vh - this.height; y += 40) {
        for (var x = 10; x <= this.vw - this.width; x += 40) {
          var line = document.createElement("div");
          document.getElementsByClassName("lines")[0].append(line);
          line.style.width = this.width + "px";
          line.style.height = this.height + "px";
          line.style.left = x + "px";
          line.style.top = y + "px";
          line.className = "line";
          this.lines.push({
            element: line,
            cx: x + this.width / 2,
            cy: y + this.height / 2,
          });
        }
      }
    }, 10);
  },
  methods: {
    mouseEnter() {
      document.getElementsByClassName("circles")[0].style.display = "none";
      document.getElementsByClassName("lines")[0].style.display = "flex";
      this.$store.commit("mouseEffectOff");
    },
    mouseMove(event) {
      this.mouse.x = event.layerX;
      this.mouse.y = event.layerY;

      if (!this.requestId) {
        this.requestId = requestAnimationFrame(this.update);
      }
    },
    update() {
      for (var i = 0; i < this.lines.length; i++) {
        var line = this.lines[i];

        var dx = this.mouse.x - line.cx;
        var dy = this.mouse.y - line.cy;

        var transform = "rotate(" + Math.atan2(dy, dx) + "rad)";
        line.element.style.transform = transform;
      }

      this.requestId = null;
    },
    mouseOut() {
      document.getElementsByClassName("circles")[0].style.display = "block";
      document.getElementsByClassName("lines")[0].style.display = "none";
      this.$store.commit("mouseEffectOn");
    },
  },
  computed: {
    changeColor() {
      const circle = document.getElementsByClassName("circle");
      setInterval(() => {
        for (let i = 0; i < circle.length; i++) {
          if (circle[i].className == "circle whitCircle") {
            circle[i].className = "circle grayCircle";
          } else {
            circle[i].className = "circle whitCircle";
          }
        }
      }, 2000);
    },
  },
};
</script>

<style>
</style>