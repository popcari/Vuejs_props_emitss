<!-- eslint-disable vue/multi-word-component-names -->
<template>
	<p>The user {{ name }} is {{ age }} year old</p>
</template>

<script>
// import { Agent } from "http";

export default {
	// eslint-disable-next-line vue/multi-word-component-names
	name: "User",
	props: ["age", "name"],
};
</script>

<style></style>
