<template>
	<div class="container">
  	<h1>Vista Proyectos</h1>
		<hr>
		<div class="row">
			<router-link to="/create" class="col s12 waves-effect waves-light btn teal">
				<i class="material-icons"> add </i> Crear Nuevo
			</router-link>
		</div>
		<contenedor />
	</div>
</template>

<script>
import Contenedor from '../components/Contenedor.vue'
export default {
  components: { Contenedor },

}
</script>

<style>

</style>