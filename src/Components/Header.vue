<template>
   <header class="header">
      <div class="header__container">
         <nav class="menu">
            <router-link to="/" >
               <h3 class="menu__title">{{title}}</h3>
            </router-link>
            <ul class="menu__list">
               <li class="menu__item" v-for="link in links" :key="link.alias">
                  <routerLink class="menu__link" :to="link.url">{{link.title}}</routerLink>
               </li>
            </ul>
         </nav>
      </div>
   </header>
</template>

<script>
import {app} from '@/_config';
import {links} from '@/_config';

export default {
  data() {
      return {
         title: app.title,
         links: links,   
      };
  },
};
</script>