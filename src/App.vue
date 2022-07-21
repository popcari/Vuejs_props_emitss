<template>
	<img alt="Vue logo" src="./assets/logo.png" />
	<hr />
	<!-- <button type="button" @click="age++">update age</button>

	<button type="button" @click="age--">downgrade age</button> -->
	<user
		:age="age"
		:name="name"
		@up-age="upAgeby2"
		@down-age="age--"
		:ageChangeFunc="upAgeby2CB"
	></user>
	<greeting :age="age"></greeting>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import User from "./components/User.vue";
import Greeting from "./components/Greeting.vue";
export default {
	name: "App",
	components: {
		User,
		Greeting,
	},
	data() {
		return {
			age: 18,
			name: "Nguyen Thanh Duy",
		};
	},
	methods: {
		upAgeby2(num) {
			this.age += num;
		},
		upAgeby2CB(num) {
			this.age += num;
		},
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
