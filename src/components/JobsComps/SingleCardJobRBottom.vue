<template>
	<section :class="$style.job_description">
		<div
			:class="[
				active ? 'description_toggle_hide' : 'description_toggle_show',
			]"
		>
			<p>
				{{ jobFromSingle.text }}
			</p>
		</div>
		<button :class="$style.description_btn_toggle" @click="toggleHide">
			Show more
			<img :src="arrowBtnToggle" alt="" />
		</button>
		<ul :class="$style.job_description_preview">
			<li>
				<h3>Nivel de antigüedad</h3>
				<span>ninguna</span>
			</li>
			<li>
				<h3>Nivel de antigüedad</h3>
				<span>ninguna</span>
			</li>
			<li>
				<h3>Nivel de antigüedad</h3>
				<span>ninguna</span>
			</li>
			<li>
				<h3>Nivel de antigüedad</h3>
				<span>ninguna</span>
			</li>
		</ul>
	</section>
</template>

<script>
import { ref } from "@vue/reactivity";
export default {
	props: ["jobFromSingle"],
	setup() {
		const active = ref(true);
		const arrowBtnToggle = ref(
			"https://iconoir.com/source/icons/nav-arrow-down.svg"
		);

		const toggleHide = () => {
			active.value = !active.value;
			if (!active.value) {
				return (arrowBtnToggle.value =
					"https://iconoir.com/source/icons/nav-arrow-up.svg");
			} else {
				return (arrowBtnToggle.value =
					"https://iconoir.com/source/icons/nav-arrow-down.svg");
			}
		};
		return {
			active,
			arrowBtnToggle,
			toggleHide,
		};
	},
};
</script>

<style>
.description_toggle_show {
	max-height: 100%;
}
.description_toggle_hide {
	max-height: 120px;
	overflow: hidden;
	position: relative;
}
.description_toggle_hide::after {
	content: "";
	position: absolute;
	bottom: 0;
	width: 100%;
	height: 60px;
	display: block;
	background: linear-gradient(0deg, #fff, #ffffff00 100%);
}
</style>

<style module>
.job_description {
	padding-top: 24px;
	padding-left: 24px;
}
.description_btn_toggle {
	background: none;
	display: block;
	position: relative;
	border: none;
	height: 40px;
	margin-top: 10px;
	margin-bottom: 20px;
	margin-right: auto;
	padding-right: 25px;
	cursor: pointer;
	border-radius: 3px;
	font-size: 0.9rem;
	font-weight: 900;
	font-family: inherit;
	color: #00000099;
	transition: background-color 0.3s ease-out, color 0.3s ease-out;
}
.description_btn_toggle img {
	position: absolute;
	top: 8px;
}
.description_btn_toggle:hover {
	background-color: rgba(0, 0, 0, 0.08);
	color: rgba(0, 0, 0, 0.9);
}
.job_description_preview {
	list-style: none;
	display: grid;
	grid-template-columns: repeat(2, 1fr);
	row-gap: 20px;
	text-align: left;
}
.job_description_preview li h3 {
	font-weight: 400;
	font-size: 0.9rem;
}
.job_description_preview li span {
	font-weight: 600;
}
</style>
