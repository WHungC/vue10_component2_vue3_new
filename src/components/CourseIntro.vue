<template>
	<li>
		<h2>{{ id }}-{{isCurrent}}</h2>
		<button @click="toggleCourseDetail">Show detail</button>
		<button @click="toggleCurrent">toggle current class</button>
		<ul v-if="detailsVisible">
			<li>{{ name }}</li>
			<li>{{ duration }}</li>
		</ul>
	</li>
</template>
<script>
export default {
	props: { 
		id: { type: String, requred: true },
		name: { type: String, requred: true },
		duration: {
			type: Number,
			requred: true,
			validator: function (value) {
				return parseInt(value) > 7;
			}
		}, 
		current: { type: Boolean, requred: false, default: false }
	},	//props can't modify value
	data() {
		return {
			detailsVisible: true,
			isCurrent: this.current
		};
	},
	methods: {
		toggleCourseDetail() {
			this.detailsVisible = !this.detailsVisible;
		},
		toggleCurrent(){
			this.isCurrent = !this.isCurrent;
			//this.current = !this.current;
		}
	},
};
</script>