<template>
  <div class="card">
    <div v-if="imgUrl" class="card-img__wrapper">
      <img class="card-img" :src="imgUrl" :alt="title">
    </div>
    <span class="card-name">{{ name }}</span>
    <span class="card-title">{{ title }}</span>
    <div class="card-body">
      <slot name="body"></slot>

      <router-link v-if="link" 
        class="link" 
        style="display: block; margin-top: 16px;" 
        :to="link"
      >See more</router-link>
    </div>
    <!-- <slot name="footer"></slot> -->
    <CardFooter :id="id"/>
  </div>
</template>

<script>
import CardFooter from '@/components/UI/CardFooter.vue'

export default {
  components: {
    CardFooter
  },
  props: {
    name: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    imgUrl: {
      type: String
    },
    link: {
      type: String
    },
    id: {
      type: Number
    }
  }
}
</script>