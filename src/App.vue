<script setup>
import {ref, reactive} from 'vue'

const carouselItems=[
  {
    image:"https://images.unsplash.com/photo-1689361319907-a7c75f63600b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    title: "frist picture",
    caption: "Lorem Ipsum is simply dummy text of the printing and typesetting industry"

  },
  {
    image:"https://images.unsplash.com/photo-1689832097085-43f8f645ebcb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=435&q=80",
    title:"second picture",
    caption:"Lorem Ipsum is simply dummy text of the printing and typesetting industry"
  },

  {
    image:"https://images.unsplash.com/photo-1689768013635-80b4d4a83693?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=435&q=80",
    title:"thrid picture",
    caption:"Lorem Ipsum is simply dummy text of the printing and typesetting industry"
  },
  {
    image:"https://images.unsplash.com/photo-1689361318708-4d242b4c4987?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=927&q=80",
    title:"fourth picture",
    caption:"Lorem Ipsum is simply dummy text of the printing and typesetting industry"
  }

]
const Index=ref(0)

</script>

<template>
   <h4>Vue Image Carousel</h4>
  
  <div id="carouselExampleCaptions" class="carousel" data-ride="carousel">    
    <ol class="carousel-indicators">
      <li @click="Index = index"  v-for="(items, index) in carouselItems" :key="index" ></li>
    </ol>
    
    <div class="carousel-inner">        
      <div class="carousel-item active">           
        <img height="600" class="d-block w-100 img img-responsive" :src="carouselItems[Index].image" >
        <div class="carousel-caption d-none d-md-block">
          <h4>{{ carouselItems[Index].title }}</h4>
          <p>{{ carouselItems[Index].caption }}</p>
          
        </div>
      </div>  
    </div>    
    <a @click.prevent="0 == Index ? Index = (carouselItems.length) - 1 : Index--" class="carousel-control-prev"  role="button" data-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Previous</span>
    </a>
    <a @click.prevent="(carouselItems.length) - 1 == Index ? Index = 0 : Index++" class="carousel-control-next"  role="button" data-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">Next</span>
    </a>
  </div>
</template>

<style scoped>
</style>
