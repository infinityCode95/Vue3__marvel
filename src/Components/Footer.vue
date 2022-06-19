<template>
   <div class="footer">
      <div class="footer__container">
            <ul class="menu__list">
               <li class="menu__item" v-for="link in links" :key="link.alias">
                  <router-link class="menu__link" :to="link.url">{{link.title}}</router-link>
               </li>
            </ul>
      </div>
   </div>
</template>

<script>
import {links} from '@/_config';

export default {
   data() {
      return {
         links: links,   
      };
  },   
};
</script>