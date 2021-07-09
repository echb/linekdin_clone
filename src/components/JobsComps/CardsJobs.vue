<template>
	<div :class="$style.content">
		<SingleCardJob
			:class="$style.content_single"
			:store="store"
			:storeLoadGlobal="storeLoadGlobal"
			@show="showMessage"
		/>
		<SingleJobR
			:jobFromSingle="jobPass.job"
			:class="$style.content_right"
		/>
	</div>
</template>

<script>
import SingleJobR from "./SingleJobR.vue";
import SingleCardJob from "./SingleCardJob.vue";
import { inject, reactive } from "@vue/runtime-core";
export default {
	components: {
		SingleCardJob,
		SingleJobR,
	},
	setup() {
		const jobPass = reactive({
			job: null,
		});
		const store = inject("store");
		const showMessage = (msg) => {
			jobPass.job = msg;
		};

		return {
			store,
			showMessage,
			jobPass,
		};
	},
};
</script>

<style module>
.content {
	display: flex;
	max-width: 1180px;
	margin-left: auto;
	margin-right: auto;
}
.content_single {
	width: 45%;
}
.content_right {
	width: 55%;
}
</style>