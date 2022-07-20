<template>
	<img alt="Vue logo" src="./assets/logo.png" />
	<!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
	<user :age="age" :name="name"></user>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import User from "./components/User.vue";
export default {
	name: "App",
	components: {
		User,
		// HelloWorld,
	},
	data() {
		return {
			age: 20,
			name: "Duy",
		};
	},
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
</style>
