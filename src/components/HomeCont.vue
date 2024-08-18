<template>
  <div class="image-swapper">
    <div class="big-image-container">
      <img :src="currentImage.src" alt="Big Image" class="big-image" />
      <div class="overlay">
        <div class="text-container">
          <!-- <div class="image-text">{{ currentImage.description }}</div>
          <button class="buy-now-btn">Buy Now</button> -->
        </div>
        <div class="thumbnails-container">
          <div
            v-for="(image, index) in images"
            :key="index"
            class="thumbnail"
            @click="swapImages(index)"
          >
            <img :src="image.src" alt="Thumbnail Image" class="small-image" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
        { src: 'H1.png' },
        { src: 'H3.jpg' },
        { src: 'H2.jpg' },
      ],
      currentIndex: 0,
    };
  },
  computed: {
    currentImage() {
      return this.images[this.currentIndex];
    },
  },
  methods: {
    swapImages(index) {
      this.currentIndex = index;
    },
  },
};
</script>

<style scoped>
html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
}

.image-swapper {
  width: 100%;
  height: 100vh;
  position: relative;
}

.big-image-container {
  width: 100%;
  height: 100%;
  position: relative;
}

.big-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  margin: 0;
  padding: 0;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 20px;
  box-sizing: border-box;
}

.text-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  height: 50%;
  max-width: 50%;
}

.thumbnails-container {
  display: flex;
  justify-content: center;
  gap: 10px;
}

.thumbnail {
  cursor: pointer;
}

.small-image {
  text-align: center;
  align-items: center;
  width: 70px;
  height: 70px;
  border: 2px solid rgb(12, 11, 11);
  border-radius: 15px;
  transition: transform 0.2s;
}

.small-image:hover {
  transform: scale(1.1);
}

@media (max-width: 600px) {
  .big-image-container {
    height: 100vh;
  }

  .text-container {
    max-width: 100%;
    padding: 10px;
  }

  .image-text {
    font-size: 14px;
  }

  .buy-now-btn {
    margin-left: 0rem;
    padding: 6px 16px;
    font-size: 14px;
    display: flex;
    margin-top: 1px;
  }

  .small-image {
    width: 60px;
    height: 60px;
  }
}
</style>
