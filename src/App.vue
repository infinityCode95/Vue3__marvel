<template>
	<div class="wrapper">
		<Header />
		<div class="main">
			<div class="main__container">
				<router-view />
			</div>
		</div>
		<Footer />
	</div>
</template>

<script>

import Header from '@/Components/Header';
import Footer from '@/Components/Footer';

export default {
	components: {
		Header, 
		Footer
	},
}

</script>

<style lang="scss"></style>
