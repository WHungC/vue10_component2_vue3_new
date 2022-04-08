<template>
	<li>
		<h2>{{ id }}-{{current}}</h2>
		<button @click="toggleCourseDetail">Show detail</button>
		<ul v-if="detailsVisible">
			<li>{{ name }}</li>
			<li>{{ duration }}</li>
		</ul>
	</li>
</template>
<script>
export default {
	props: { id: String, name: String, duration: Number, current: Boolean },	//props can't modify value
	data() {
		return {
			detailsVisible: true,
		};
	},
	methods: {
		toggleCourseDetail() {
			this.detailsVisible = !this.detailsVisible;
		},
	},
};
</script>