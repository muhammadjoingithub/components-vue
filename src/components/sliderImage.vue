<template>
  <div class="image-gallery mt-20 mx-auto">
    <img class="image-1" @mouseover="toggleHover(1)" @mouseleave="toggleHover(1)" src="../assets/vue1.png" />
    <img class="image-2" @mouseover="toggleHover(2)" @mouseleave="toggleHover(2)" src="../assets/vue2.png" />
    <img class="image-3" @mouseover="toggleHover(3)" @mouseleave="toggleHover(3)" src="../assets/vue3.png" />
    <img class="image-4" @mouseover="toggleHover(4)" @mouseleave="toggleHover(4)" src="../assets/vue4.png" />
    <img class="image-5" @mouseover="toggleHover(5)" @mouseleave="toggleHover(5)" src="../assets/vue5.png" />
  </div>
</template>

<script>
export default {
  methods: {
    toggleHover(imageNumber) {
      const imageClass = `image-${imageNumber}`;
      const imageElement = document.querySelector(`.${imageClass}`);
      imageElement.classList.toggle('hover');
    }
  }
};
</script>

<style scoped>
.image-gallery {
  display: flex;
  gap: 20px;
  justify-content: center;
}

.image-gallery img {
  object-fit: cover;
  transition: filter 0.5s ease;
}

.image-gallery img.hover {
  filter: brightness(1.2); 
  transform: scale(1.1);
  object-fit: cover;
}
</style>