<template>
	<section :class="$style.job_card">
		<div :class="$style.job_icon">
			<a href="#">
				<img
					src="https://static-exp1.licdn.com/sc/h/9a9u41thxt325ucfh5z8ga4m8"
					alt=""
				/>
			</a>
		</div>
		<div :class="$style.job_content">
			<a href="#" :class="$style.job_link">
				<h2>{{ jobFromSingle.position }}</h2>
			</a>
			<div :class="$style.job_content_description">
				<div :class="$style.job_second_line">
					<span :class="$style.job_link_corp">
						<a href="#">
							{{ jobFromSingle.corporation }}
						</a>
					</span>
					<span :class="$style.job_link_location">
						{{ jobFromSingle.city }}, {{ jobFromSingle.state }},
						{{ jobFromSingle.country }}
					</span>
				</div>
				<div>
					<span :class="$style.job_link_time">
						{{ jobFromSingle.time }}
					</span>
					<span
						v-if="jobFromSingle.applied >= 26"
						:class="$style.job_applied_less_25"
					>
						{{ jobFromSingle.applied }} applied
					</span>
					<span v-else :class="$style.job_applied_25">
						Be of the first 25 to apply
					</span>
				</div>
				<div :class="$style.job_content_description_bottom">
					<button
						:class="$style.job_content_description_bottom_website"
					>
						web-site
					</button>
					<button :class="$style.job_content_description_bottom_save">
						save
					</button>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	props: ["jobFromSingle"],
};
</script>

<style module>
.job_card {
	position: relative;
	padding: 24px;
	border-radius: 5px;
	box-shadow: 0px -1px 1px #00000014, 1px 0px 1px #00000014,
		-1px 0px 1px #00000014, 0px 1px 1px #00000014;
}
.job_icon {
	display: flex;
	justify-content: left;
}
.job_icon a img {
	width: 72px;
	height: 72px;
}
.job_link {
	text-decoration: none;
	color: inherit;
}
.job_link :hover {
	text-decoration: underline;
}
.job_content {
	text-align: left;
}
.job_second_line {
	margin-top: 5px;
	margin-bottom: 10px;
}
.job_link_corp a {
	color: inherit;
	text-decoration: none;
	font-size: 1rem;
	font-weight: 500;
}
.job_link_corp a:hover {
	color: #0a66c2;
	text-decoration: underline;
}
.job_link_location {
	position: relative;
	text-transform: capitalize;
	padding-left: 10px;
	margin-left: 10px;
}
.job_link_location::after {
	content: "";
	position: absolute;
	width: 2px;
	height: 2px;
	border-radius: 100%;
	display: block;
	background-color: #000;
	left: 0;
	top: 50%;
	transform: translateY(calc(50% - 2px));
}
.job_link_time {
	font-size: 0.9rem;
}
.job_applied_less_25,
.job_applied_25 {
	font-size: 0.9rem;
	position: relative;
	margin-left: 10px;
	padding-left: 10px;
}
.job_applied_less_25::after,
.job_applied_25::after {
	content: "";
	position: absolute;
	width: 2px;
	height: 2px;
	border-radius: 100%;
	display: block;
	background-color: #000;
	left: 0;
	top: 50%;
	transform: translateY(calc(50% - 2px));
}
.job_content_description_bottom {
	display: flex;
	justify-content: flex-start;
	margin-top: 20px;
}
.job_content_description_bottom_website,
.job_content_description_bottom_save {
	border: none;
	background: none;
	display: block;
	cursor: pointer;
	padding-top: 5px;
	padding-bottom: 5px;
	padding-left: 20px;
	padding-right: 20px;
	border-radius: 20px;
}
.job_content_description_bottom_website {
	background-color: #0a66c2;
	color: #fff;
	width: 50%;
	margin-right: 40px;
	font-size: 0.9rem;
	font-weight: 500;
	transition: background-color 0.2s ease-out;
}
.job_content_description_bottom_website:hover {
	background-color: #004182;
}
.job_content_description_bottom_save {
	border: solid 1px #0a66c2;
	display: block;
	width: 20%;
	height: 40px;
	color: #0a66c2;
	font-weight: 500;
	font-size: 0.9rem;
}
.job_content_description_bottom_save:hover {
	background-color: #eaf4fe;
	border: solid 2px #0a66c2;
}
</style>