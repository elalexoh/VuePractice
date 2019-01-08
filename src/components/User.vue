<template lang="html">
	<div class="users">
		<h1>User Component</h1>
		<ul>
			<li v-for="user in users">
				{{ user.name }} - {{ user.email }} 
				<button v-on:click="dropUser(user)">X</button>
			</li>
		</ul>
		<form v-on:submit.prevent="addUser"><!-- .prevent previene la accion por defecto del formulario -->
			<input type="text" v-model="newUser.name" placeholder="Nombre de usuario"> 
			<input type="email" v-model="newUser.email" placeholder="Correo">
			<button type="submit">
				Agregar
			</button>
		</form>
	</div>
</template>
<script>
	export	default {
		data() {
			return {
				users: [
					{
						name: 'Joe',
						email: 'Joe@gmail.com',
						telefono: '414-555-7777',
						contacted: false
					},
					{
						name: 'Deeply',
						email: 'Deeply@gmail.com',
						telefono: '414-555-7777',
						contacted: false
					},
					{
						name: 'Bloody',
						email: 'Bloody@gmail.com',
						telefono: '414-555-7777',
						contacted: true
					},
				],
				newUser: {}
			}
		},
		methods: {
			addUser() {
				this.users.push(this.newUser);
				this.newUser = {};
			},
			dropUser(user){
				this.users.splice(this.users.indexOf(user), 1);
			}

		}

	}
</script>
<style lang="css">
	.users{
		padding: 2rem;
		background-color: teal;
		color: white;

	}
	.users ul li{
		list-style:none;
		padding: 2rem;
	}
</style>