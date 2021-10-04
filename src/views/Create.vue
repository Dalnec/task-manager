<template>
	<div class="container">
		<div class="row">
			<router-link to="/proyectos" class="col s12 waves-effect waves-light btn amber darken-3">
				<i class="material-icons"> arrow_back </i> Regresar a Lista
			</router-link>
		</div>
  <div class="row">
    <form class="col s12" @submit.prevent="createProject">
				<div class="row">
					<div class="input-field col s12">
						<input id="first_name" type="text" class="validate" v-model="project.title">
						<label for="first_name">Título</label>
					</div>
					<div class="input-field col s12">
						<input id="last_name" type="text" class="validate" v-model="project.description">
						<label for="last_name">Descripcion</label>
					</div>
					<p>
						<label>
							<input type="checkbox" checked="checked" v-model="project.langs" value="HTML"/>
							<span>HTML</span>
						</label>
					</p>
					<p>
						<label>
							<input type="checkbox" checked="checked" v-model="project.langs" value="CSS"/>
							<span>CSS</span>
						</label>
					</p>
					<p>
						<label>
							<input type="checkbox" checked="checked" v-model="project.langs" value="Python"/>
							<span>Python</span>
						</label>
					</p>
					<p>
						<label>
							<input type="checkbox" checked="checked" v-model="project.langs" value="Javascript"/>
							<span>Javascript</span>
						</label>
					</p>
					<button class="btn waves-effect waves-light col s12" type="submit" name="action">Guardar
						<i class="material-icons right">send</i>
					</button>
      	</div>
    </form>
		</div>
		{{project}}
  </div>
</template>

<script>
export default {
	data(){
		return{
			project:{
				description:"",
				langs:[],
				title:"",
				status: true
			}
		}
	},
	methods:{
		async createProject(){
			const res = await fetch("https://crud-vue-bfe02-default-rtdb.firebaseio.com/projects.json", 
				{
					method:"POST",
					body: JSON.stringify(this.project),
				}
			);
		},
	}
}
</script>

<style>

</style>