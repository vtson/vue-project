<template>
  <div class="image-gallery">
    <div class="image-container" v-for="(image, index) in images" :key="index" @click="toggleSelection(index)">
      <img :src="image.thumbnail" :alt="image.alt">
      <div class="selection-overlay" v-if="selectedImages.includes(index)">
        <i class="el-icon-check"></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ImageGallery',
  props: {
    images: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      selectedImages: [],
    };
  },
  methods: {
    toggleSelection(index) {
      const selectedIndex = this.selectedImages.indexOf(index);

      if (selectedIndex > -1) {
        this.selectedImages.splice(selectedIndex, 1);
      } else {
        this.selectedImages.push(index);
      }
    },
  },
};
</script>

<style scoped>
.image-gallery {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  border: 1px solid #dcdfe6;
  border-radius: 1%;
  margin-bottom: 20px;
  padding: 20px;
}

.image-container {
  position: relative;
  width: calc(33.33% - 10px);
  margin: 5px 0;
  cursor: pointer;
  transition: transform 0.2s ease;
}

.image-container:hover {
  transform: scale(1.05);
}

.image-container img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.selection-overlay {
  position: absolute;
  top: 2px;
  right: 2px;
  width: 10px;
  height: 10px;
  background-color: rgba(0, 128, 0, 0.8);
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  filter: brightness(120%);
  background-image: linear-gradient(to bottom, rgba(255,255,255,0.4) 0%, rgba(255,255,255,0) 100%);
}

.el-icon-check {
  color: white;
}
</style>
