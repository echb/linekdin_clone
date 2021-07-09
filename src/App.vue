<template>
	<MainLinkedin />
</template>

<script>
import store from "./stored/store.js";
import MainLinkedin from "./components/Main/MainLinkedin.vue";
import { provide } from "@vue/runtime-core";

export default {
	name: "App",
	components: {
		MainLinkedin,
	},
	setup() {
		provide("store", store);
		return {};
	},
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600&display=swap");
* {
	margin: 0;
	padding: 0;
	font-family: "Montserrat", sans-serif;
}
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
}
</style>
