<template>
  <div class="slide">
    <div class="content">
      <h1>Slide title here</h1>
      <p>This is a paragraph</p>
      <ul>
        <li>this is a list item</li>
        <li>another one...</li>
        <li>one more...</li>
        <li>and finally this list item</li>
      </ul>
    </div>
    <div class="image">
      <img src="../assets/nyan.jpg" alt="nyan cat" />
    </div>
  </div>
</template>

<script>
export default {
  name: "SlideTemplate"
};
</script>

<style>
.slide {
  background: #77b9f1;
  padding: 30px;
  height: 100vh;
  box-sizing: border-box;
  display: flex;
  justify-content: space-between;
}
</style>
