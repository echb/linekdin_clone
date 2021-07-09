<template>
	<section :class="$style.single_job">
		<ul :class="$style.single_job_container">
			<li
				@click="more"
				v-for="job in store.jobs"
				:key="job"
				:class="$style.single_job_box"
			>
				<a
					href=""
					@click.prevent="show(job)"
					:class="$style.single_job_item"
				>
					<div :class="$style.single_job_icon">
						<img
							src="https://static-exp1.licdn.com/sc/h/9a9u41thxt325ucfh5z8ga4m8"
							alt=""
						/>
					</div>
					<div :class="$style.single_job_content">
						<h3 :class="$style.single_job_title">
							{{ job.position }}
						</h3>
						<h4 :class="$style.single_job_description">
							{{ job.corporation }}
						</h4>
						<div :class="$style.single_job_data">
							<span :class="$style.single_job_location">
								{{ job.city }}, {{ job.state }},
								{{ job.country }}
							</span>
							<span :class="$style.single_job_time">
								{{ job.time }}
							</span>
						</div>
					</div>
				</a>
			</li>
		</ul>
	</section>
</template>

<script>
export default {
	props: ["store"],
	setup(props, { emit }) {
		const show = (job) => {
			emit("show", job);
		};
		// const loaded = ref(props.store.jobs);
		// const add = ref(3);

		// loaded.value = loaded.value.slice(0, add.value);

		// const more = () => {
		// 	const loadedd = ref(props.store.jobs);
		// 	add.value++;
		// 	loadedd.value = loadedd.value.slice(0, add.value);
		// 	loaded.value = loadedd.value;
		// };
		return { show };
	},
};
</script>

<style module>
.single_job_container {
	margin: 0;
	padding: 0;
	list-style: none;
	border-right: 1px solid #e6e9ec;
}
.single_job_container li.single_job_box:hover {
	background-color: #f2f5f7;
}
.single_job_item {
	display: flex;
	text-decoration: none;
	color: inherit;
	padding: 12px 16px 12px 8px;
	border-bottom: 1px solid #e6e9ec;
}
.single_job_item:hover > .single_job_content .single_job_title {
	text-decoration: underline;
	text-decoration-thickness: 1px;
}
.single_job_icon {
	margin-right: 8px;
}
.single_job_icon img {
	width: 48px;
	height: 48px;
}
.single_job_content {
	text-align: left;
}
.single_job_title {
	font-size: 1.3rem;
	font-weight: 600;
}
.single_job_description {
	font-size: 1rem;
	font-weight: 500;
}
.single_job_data span {
	display: block;
	font-size: 0.9rem;
}
.single_job_location {
	text-transform: capitalize;
}
</style>