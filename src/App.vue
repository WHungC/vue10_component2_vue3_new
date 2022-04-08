<template>
	<new-course @add-course="addCourse"></new-course>
  <course-intro
    v-for="course in courses"
    :key="course.id"
    :id="course.id"
    :name="course.name"
    :duration="course.duration"
    :current="course.current"
    @delete-current="delCourse"
  ></course-intro>
</template>

<script>
export default {
	name: "App",
	data() {
		return {
			courses: [
				{ id: "poop", name: "python oop", duration: 35, current: true },
				{
					id: "bdpy",
					name: "python and big data",
					duration: 35,
					current: false,
				},
			],
		};
	},
  created(){
    console.log("component created")
    this.emitter.on('toggle-current',(idx)=>{
      console.log(`${idx} should change toggle state`);
      const course = this.courses.find((c) => c.id == idx);
      course.current = !course.current;
    })
  },
  methods:{
    addCourse(id, name, duration){
      const newCourse = {id:id, name:name, duration:parseInt(duration),current:false}
      this.courses.push(newCourse)
    },
    delCourse(id){
      this.courses = this.courses.filter((course)=>course.id !== id)
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#app ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
#app li,
#app form {
  box-shadow: 0 4px 8px rgba(0, 0, 128, 0.26);
  margin: 1rem auto;
  padding: 1rem;
  border-radius: 5px;
  text-align: center;
  width: 50%;
  max-width: 40rem;
}
#app button {
  font: inherit;
  cursor: pointer;
  border: 1px sold #ff0077;
  background-color: #c0ffee;
  color: black;
}
</style>
