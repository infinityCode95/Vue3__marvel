<template>
   <div class="card">
      <div v-if="imgUrl" class="card__img-wrapper">
         <img class="card__img" :src="imgUrl" :alt="title">
      </div>
      <span class="card__name">{{name}}</span>
      <span class="card__title">{{title}}</span>
      <div class="card__body">
         <slot name="descr"></slot>
         <router-link class="card__btn" v-if="link" :to="link">Открыть</router-link>
      </div>
   </div>
</template>

<script>
export default {
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
         type: String,
      },

      link: {
         type: String,
      },
   }
}
</script>