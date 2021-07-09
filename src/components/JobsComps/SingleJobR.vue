<template>
	<section v-if="jobFromSingle" :class="$style.job_section">
		<div :class="$style.job_box">
			<SingleCardJobRTop :jobFromSingle="jobFromSingle" />
			<SingleCardJobRBottom
				@showHideDescription="toggleHide"
				:jobFromSingle="jobFromSingle"
			/>
		</div>
	</section>
</template>

<script>
import SingleCardJobRTop from "./SingleCardJobRTop.vue";
import SingleCardJobRBottom from "./SingleCardJobRBottom.vue";

export default {
	components: {
		SingleCardJobRTop,
		SingleCardJobRBottom,
	},
	props: ["jobFromSingle"],
	setup() {
		return {
			SingleCardJobRTop,
			SingleCardJobRBottom,
		};
	},
};
</script>

<style module>
.job_section {
	margin-top: 10px;
	padding-left: 10px;
	padding-right: 10px;
}
.job_box {
	position: sticky;
	top: 10px;
	height: calc(100vh - 10px);
	overflow: auto;
	padding: 1px;
}
</style>