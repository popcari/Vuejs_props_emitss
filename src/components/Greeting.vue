<template>
	<p v-if="age >= 25">{{ message }}</p>
	<p v-else>You must be 25 or older to view this message</p>
</template>

<script>
export default {
	// eslint-disable-next-line vue/multi-word-component-names
	name: "Greeting",
	props: ["age"],
	data() {
		return {
			message: "Hello handsome man",
		};
	},
};
</script>

<style></style>
