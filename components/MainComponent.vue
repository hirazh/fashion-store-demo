<template>
  <div class="container">
    <div class="fabric-container">
      <h3>Fabric</h3>
      <div class="fabric-image" v-for="(item, id) in myDatabase" :key="id">
        <p>{{ item.isPreview }}</p>
        <img :src="item.fabric" @click="previewClothe(id)">
      </div>
    </div>
    <div class="preview-container">
      <h3>Clothe Preview</h3>
      <div class="clothe-image" v-for="(clothe, x) in myDatabase" :key="x">
        <div v-if="clothe.isPreview">
          <img :src="clothe.previewImage">
          <span>
            <button @click="previewClothe(x)">close</button>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      //this object is like a database for the sample clothes
      myDatabase: [
        {
          id: 1,
          name: "Blue",
          fabric: require("../static/images/blue.jpeg"),
          previewImage: require("../static/images/blue-shirt.jpeg"),
          isPreview: false
        },
        {
          id: 2,
          name: "Black",
          fabric: require("../static/images/black.jpeg"),
          previewImage: require("../static/images/black-shirt.jpeg"),
          isPreview: false
        },
        {
          id: 3,
          name: "flower",
          fabric: require("../static/images/flower.jpeg"),
          previewImage: require("../static/images/flower-shirt.jpeg"),
          isPreview: false
        },
        {
          id: 4,
          name: "purple",
          fabric: require("../static/images/purple.jpeg"),
          previewImage: require("../static/images/purple-shirt.jpeg"),
          isPreview: false
        }
      ]
    };
  },
  methods: {
    //this function toggle the isPreview property from false to true and vice verca
    previewClothe: function(id) {
      const index = this.myDatabase.findIndex(db => db.id === id);
      this.myDatabase[index + 1].isPreview = !this.myDatabase[index + 1].isPreview;
    }
  }
};
</script>

<style scoped>
h3 {
  margin-bottom: 15%;
}
.container {
  display: grid;
  grid-template-columns: 1fr 2fr;
}
.fabric-image img {
  width: 100px;
  padding: 5%;
  cursor: pointer;
}
.clothe-image img {
  width: 250px;
  padding: 2%;
}

.clothe-image button {
  position: relative;
  top: -250px;
  padding: 5px;
  background-color: red;
  color: #f0f0f0;
}
</style>
