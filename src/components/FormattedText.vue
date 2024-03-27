<template>
	<div>
		<div class="container">
			<div class="row" :class="{'flex-row-reverse': imgPosition == 'left'}">
				<div :class="{
						'col-12 col-lg-6 pb-5 pb-lg-0': imgSrc,
						'col-12 col-lg-12 text-center': !imgSrc,
						'pl-lg-20': imgPosition == 'left',
						'pr-lg-20': imgPosition == 'right',
						'd-flex': contentClasses}">
					<div :class="contentClasses">
						<slot></slot>
					</div>
				</div>
				<div v-if="imgSrc"
					class="col-12 col-lg-6"
					:class="{
						'pr-lg-20': imgPosition == 'left',
						'pl-lg-20': imgPosition == 'right',
					}">
					<img :src="imgSrc" class="img-fluid" alt="">
				</div>
			</div>
		</div>
	</div>
</template>

<script>
  export default {
	props: ['imgSrc', 'imgPosition', 'contentClasses']
  }
</script>

<style>

</style>