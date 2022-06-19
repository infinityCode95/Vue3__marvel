<template>
   <div class="home">
      <div class="home__container">
			<carousel :settings="settings" :breakpoints="breakpoints">
				<slide class="card__wrapper" v-for="hero in heroes" :key="hero.id">
					<Card 
						:name="`${hero.lvl} lvl`" 
						:title="hero.title" 
						:imgUrl="hero.img" 
						:link="`/${hero.alias}`"
					>
						<template v-slot:descr>
							{{hero.descr}}
						</template>
					</Card>
				</slide>

				<!-- addons -->
				<template #addons>
					<navigation />
				</template>
  			</carousel>
      </div>
   </div>
</template>

<script>
import Heroes from '@/seeders/heroes';
import Card from '@/Components/UI/Card';

import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Navigation } from 'vue3-carousel';


export default {
   components: {
      Card,
		Carousel,
		Slide,
		Navigation, 
   },

	data() {
		return {
			heroes: Heroes,
			settings: {
				itemsToShow: 2,
				wrapAround: true,
				snapAlign: 'center',
			},
			breakpoints: {
				300: {
					itemsToShow: 1,
				},
				700: {
					itemsToShow: 2,
				},
			}
		}
	}
}
</script>
