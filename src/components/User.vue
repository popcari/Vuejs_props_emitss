<template>
	<div class="button">
		<button type="button" @click="upAge">update age event</button>
		<button type="button" @click="downAge">downgrade age</button>
		<!-- test callback function -->
		<button type="button" @click="ageChangeFunc(3)">
			Age +3(callback function)
		</button>
	</div>
	<p>The user {{ name }} is {{ age }} year old</p>
	<p>{{ agex2 }}</p>
	<p>{{ agex3 }}</p>
</template>

<script>
export default {
	// eslint-disable-next-line vue/multi-word-component-names
	name: "User",
	props: {
		age: {
			type: Number,
			require: true,
		},
		name: {
			type: String,
			require: true,
		},
		ageChangeFunc: Function,
	},
	emits: ["up-age"],
	computed: {
		agex2() {
			return this.age * 2;
		},
		agex3() {
			return this.age * 3;
		},
	},
	methods: {
		upAge() {
			this.$emit("up-age", 2);
		},
		downAge() {
			this.$emit("down-age");
		},
	},
};
</script>

<style scoped>
p {
	color: rgb(8, 172, 62);
}
.button {
	display: flex;
	justify-content: space-between;
}
button {
	cursor: pointer;
	color: white;
	background-image: linear-gradient(to right, #069862, rgba(22, 38, 53, 0.897));
}
</style>
