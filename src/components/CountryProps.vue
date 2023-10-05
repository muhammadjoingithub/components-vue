<template>
  <div class="boxes">
    <div
      class="items mt-20 "
      v-for="(item, index) in items"
      :key="index"
      @mouseover="toggleHover(index)"
      @mouseleave="toggleHover(null)"
      :style="{ transform: index === activeIndex ? 'scale(1.3)' : 'none' }"
    >
      <img src='../assets/vue11.png' :alt="item.alt" />
      <h3>{{ item.title }}</h3>
      <p>{{ item.description }}</p>
      <div class="bottom-border"></div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    items: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      activeIndex: null
    };
  },
  methods: {
    toggleHover(index) {
      this.activeIndex = index;
    }
  }
};
</script>

<style scoped>
.boxes {
  display: flex;
  justify-content: center;
  gap: 40px;
  padding: 40px;
}

.items {
  display: flex;

  flex-direction: column;
  align-items: center;
  text-align: center;
  /* width: 150px; */
  padding: 50px;
  background-color: rgb(34, 32, 32);
 transition: transform 0.3s ease;
}

.items img {
  width: 100%;
  height: auto;
  margin-bottom: 10px;
}

.items h3 {
  font-size: 16px;
  margin-bottom: 5px;
}

.items p {
  font-size: 14px;
  color: #999;
}

.items .bottom-border {
  width: 100%;
  height: 4px;
  background-color: #ccc;
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

.items:hover .bottom-border {
  transform: scaleX(1);
}
</style>