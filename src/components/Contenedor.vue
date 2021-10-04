<template>
  <div class="row">
		<div class="col s12">
			<Card v-for="(project, index) in projects" :key="index" :data="project" />
		</div>
	</div>
</template>

<script>
import Card from './Card.vue'
export default {
	data: () => ({
		projects: [],
	}),
  components: { Card },
	mounted(){
		this.getProjects();
	},
	methods:{
		async getProjects(){
			const res = await fetch("https://crud-vue-bfe02-default-rtdb.firebaseio.com/projects.json");
			const data = await res.json();
			for (const i in data) {
				// this.projects.push(data[i]);
				this.projects.push({
					id: i,
					data: data[i]
				});
			}
		},
	},
}
</script>

<style>

</style>