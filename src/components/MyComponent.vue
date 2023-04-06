<template>
  <div class="my-component">
    <div class="row">
      <div class="col-4">
        <el-input v-model="videoTitle" placeholder="Video title"></el-input>
      </div>
      <div class="col-8">
        <el-row class="search-area">
          <el-col :span="17">
            <el-input v-model="searchImageKeyWord" placeholder="Search image keyword"></el-input>
          </el-col>
          <el-col :span="5">
            <el-button type="success" @click="searchImage">Search</el-button>
          </el-col>
        </el-row>
      </div>
    </div>
    <div class="row">
      <div class="col-4">
        <el-input type="textarea" :rows="20" v-model="contentScript" placeholder="Content script"></el-input>
      </div>
      <div class="col-8">
        <image-gallery :images="images"></image-gallery>
        <el-upload
          :auto-upload="false"
          :on-change="handleChange"
          :before-upload="beforeUpload"
        >
          <el-button type="primary">Background music</el-button>
        </el-upload>
      </div>
    </div>
    <div class="row">
      <div class="col-4">
        <el-button type="success" @click="generateVideo">Generate Now</el-button>
      </div>
      <div class="col-8">
        <el-progress :percentage="progress" :status="progressStatus" :text-inside="true" :stroke-width="20"/>
      </div>
    </div>
  </div>
</template>

<script>
import ImageGallery from "./ImageGallery.vue";

export default {
  name: "MyComponent",
  components: {
    ImageGallery,
  },
  data() {
    return {
      videoTitle: "",
      searchImageKeyWord: "",
      search: "",
      contentScript: "",
      images: [{'thumbnail' : 'https://media.istockphoto.com/id/1322277517/photo/wild-grass-in-the-mountains-at-sunset.jpg?s=612x612&w=0&k=20&c=6mItwwFFGqKNKEAzv0mv6TaxhLN3zSE43bWmFN--J5w=','alt' : 'text'},{'thumbnail' : 'https://images.freeimages.com/images/previews/ac9/railway-hdr-1361893.jpg','alt' : 'text'},{'thumbnail' : 'https://images.unsplash.com/photo-1566438480900-0609be27a4be?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8M3x8aW1hZ2V8ZW58MHx8MHx8&w=1000&q=80','alt' : 'text'},{'thumbnail' : 'https://media.istockphoto.com/id/1322277517/photo/wild-grass-in-the-mountains-at-sunset.jpg?s=612x612&w=0&k=20&c=6mItwwFFGqKNKEAzv0mv6TaxhLN3zSE43bWmFN--J5w=','alt' : 'text'},{'thumbnail' : 'https://images.freeimages.com/images/previews/ac9/railway-hdr-1361893.jpg','alt' : 'text'},{'thumbnail' : 'https://images.unsplash.com/photo-1566438480900-0609be27a4be?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8M3x8aW1hZ2V8ZW58MHx8MHx8&w=1000&q=80','alt' : 'text'}],
      progress: 50,
      progressStatus: "primary"
    };
  },
  methods: {
    onClick() {
    },
    handleChange(file) {
    },
    beforeUpload(file) {
    },
    searchImage() {
    },
    generateVideo() {
    }
  },
};
</script>

<style scoped>
.my-component .row {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-bottom: 20px;
}
.my-component .col-4 {
  width: calc(33.33% - 10px);
}
.my-component .col-8 {
  width: calc(66.66% - 10px);
}

.search-area {
  justify-content: space-between;
}

.search-area button {
  width: -webkit-fill-available;
}
</style>
