<template>
	<div class="hero__wrapper">
		<div v-if="hero" class="hero">
			<div class="hero__flex">
				<div class="hero__img-wrapper">
					<img class="hero__img" :src="hero.img" :alt="hero.descr">
				</div>
				<div class="hero__body">
					<h1 class="hero__title">{{hero.title}}</h1>
					<p class="hero__text">
						{{hero.info}}
					</p>
					
					<div class="hero__skills">
						<div v-for="(skill, index) in hero.skills" :key="index" class="hero__skill skill">
							<span class="skill__item-value">{{skill.value}}</span>
							<span class="skill__item-title">{{skill.title}}</span>
						</div>	
					</div>
					<button class="hero__btn">
						<router-link to="/">Назад</router-link>
					</button>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import heroes from '@/seeders/heroes';

export default {
   data () {
      return {
         hero: null
      }
   },

   created () {
      const alias = this.$route.params.heroAlias
      const hero = heroes.find(el => el.alias === alias)

		this.hero = hero
   }
}
</script>