<template>
	<HelloWorld msg="Welcome to Your Vue.js App" />
	<course-intro :id="course_name1" name="python oop" :duration="35" :current="true"></course-intro>
	<course-intro :id="course_name2" name="python and big data" :duration="35" :current="false"></course-intro>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
	name: "App",
	components: {
		HelloWorld,
	},
  data() {
    return { course_name1: "POOP", course_name2: "BDPY" };
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
#app li {
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
