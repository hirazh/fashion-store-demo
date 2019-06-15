<template>
  <div class="container">
    <h1 class="title">Fashion Store</h1>
    <div class="main-container">
      <MainComponent />
    </div>
  </div>
</template>

<script>
import MainComponent from '../components/MainComponent.vue'
export default {
  components: {
    MainComponent
  }
}
</script>

<style>
.container {
  margin: 2% 8% 2% 8%;
}

.title {
 text-align: center;
 padding-bottom: 5%;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
