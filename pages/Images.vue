<template>
  <div class="about">
    <h1>toggle picture group using conditional rendering</h1>
    <p>"Generally speaking, v-if has higher toggle costs while v-show has higher initial render costs. So prefer v-show if you need to toggle something very often, and prefer v-if if the condition is unlikely to change at runtime."</p>
    <h1 v-if="counter==0">Now you see all pictures</h1>
    <h1 v-else>Now you don't</h1>
    <div class="row">
      <!-- Grid column -->
      <div class="col-md-12 d-flex justify-content-center mb-5">
        <button v-on:click="counter=0" type="button" class="btn btn-outline-black waves-effect" data-rel="all">All</button>
        <button v-on:click="counter=1" type="button" class="btn btn-outline-black waves-effect" data-rel="1">Mountains</button>
        <button v-on:click="counter=2" type="button" class="btn btn-outline-black waves-effect" data-rel="2">Sea</button>
      </div>
      <!-- Grid column -->
    </div>
    <!-- Grid row -->
    <div class="gallery" id="gallery">
      <!-- Grid column -->
      <GridImage v-for="item in pictures" v-bind:key="item.id"  v-show="counter==item.group || counter==0" v-bind:src="item.src" v-bind:alt="item.class" />
      <!-- Grid column -->
    </div>
  </div>
</template>

<script>
import GridImage from '@/components/GridImage.vue'

export default {
  name: 'imagepage',
  components: {
    GridImage
  },
  data () {
    return {
      counter: 0,
      pictures: [
        { group: '1', alt: 'random', src: 'https://mdbootstrap.com/img/Photos/Horizontal/Nature/4-col/img%20(73).jpg' },
        { group: '2', alt: 'random', src: 'https://mdbootstrap.com/img/Photos/Vertical/mountain1.jpg' },
        { group: '1', alt: 'random', src: 'https://mdbootstrap.com/img/Photos/Vertical/mountain2.jpg' },
        { group: '2', alt: 'random', src: 'https://mdbootstrap.com/img/Photos/Horizontal/Nature/4-col/img%20(35).jpg' },
        { group: '1', alt: 'random', src: 'https://mdbootstrap.com/img/Photos/Horizontal/Nature/4-col/img%20(18).jpg' },
        { group: '2', alt: 'random', src: 'https://mdbootstrap.com/img/Photos/Vertical/mountain3.jpg' }
      ]
    }
  },
  head () {
    return {
      title: 'Image',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'Image', name: 'Image', content: 'Image description' }
      ]
    }
  },
}
</script>

<style>
.gallery {
-webkit-column-count: 3;
-moz-column-count: 3;
column-count: 3;
-webkit-column-width: 33%;
-moz-column-width: 33%;
column-width: 33%; }
.gallery .pics {
-webkit-transition: all 350ms ease;
transition: all 350ms ease; }
.gallery .animation {
-webkit-transform: scale(1);
-ms-transform: scale(1);
transform: scale(1); }

@media (max-width: 450px) {
.gallery {
-webkit-column-count: 1;
-moz-column-count: 1;
column-count: 1;
-webkit-column-width: 100%;
-moz-column-width: 100%;
column-width: 100%;
}
}

@media (max-width: 400px) {
.btn.filter {
padding-left: 1.1rem;
padding-right: 1.1rem;
}
}
</style>
