<template>
  <div class="presentation">
    <div class="slide" v-show="currentSlide === 0">
      <div class="content">
        <h1>Slide 1 title here</h1>
        <p>This is a paragraph</p>
        <ul>
          <li>this is a list item</li>
          <li>another one...</li>
          <li>one more...</li>
          <li>and finally this list item</li>
        </ul>
      </div>
      <div class="image">
        <img src="./assets/nyan.jpg" alt="nyan cat" />
      </div>
    </div>
    <div class="slide" v-show="currentSlide === 1">
      <div class="content">
        <h1>Slide 2 title here</h1>
        <p>This is a paragraph</p>
        <ul>
          <li>this is a list item</li>
          <li>another one...</li>
          <li>one more...</li>
          <li>and finally this list item</li>
        </ul>
      </div>
      <div class="image">
        <img src="./assets/nyan.jpg" alt="nyan cat" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  components: {},
  data() {
    return {
      currentSlide: 0
    };
  },
  computed: {
    slides() {
      return document.querySelectorAll(".slide");
    }
  },
  methods: {
    next() {
      if (this.currentSlide < this.slides.length - 1) {
        this.currentSlide++;
      } else {
        this.currentSlide = 0;
      }
    },
    previous() {
      if (this.currentSlide > 0) {
        this.currentSlide--;
      } else {
        this.currentSlide = this.slides.length - 1;
      }
    }
  },
  created() {
    document.body.onkeyup = event => {
      switch (event.keyCode) {
        case 37: // left arrow
          this.previous();
          break;
        case 39: // right arrow
        case 32: // spacebar
          this.next();
          break;
      }
    };
    document.addEventListener("click", () => {
      this.next();
    });
  }
};
</script>

<style lang="scss">
.slide {
  background: #77b9f1;
  padding: 30px;
  height: 100vh;
  box-sizing: border-box;
  display: flex;
  justify-content: space-between;
}
</style>
