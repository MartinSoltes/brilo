<template>
  <Home/>
</template>

<script>
import Home from '/src/views/Home.vue'

export default {
	name: 'App',
	components: { Home }
}
</script>

<style lang="less">
	@import "/src/styles/bootstrap.min.css";
	@import "/src/styles/main.less";

	#app {
		margin-top: 104px;
		box-sizing: border-box;
	}
</style>
