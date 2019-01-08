<template>
	<div class="componente">
		{{ msg }}
	</div>
</template>
<script>
	export default {
		data(){ //informacion
			return {
				title: "hola Vuejs", //string
				user: { //objeto
					firstName: 'Joe',
					lastName: 'Doe'
				},
				myHtml: '<h3>hola vue</h3>', //html embedido
				showName: true, //boleano
				tasks: [ //array
					{title: 'eat'},
					{title: 'dinner'},
					{title: 'Fuck'}
				]
			}
		},
		methods: { //metodos
			saludar(name) {
				alert('hello, ' + name)
			},
			typedEnter (e) {
				console.log('diste el enter');
			}
		},
		computed: { //metodo que se autoregula
			fullName() {
				return this.user.firstName + ' ' + this.user.lastName;
			}
		},
		props: { //propiedades desde componente padre app.vue
			msg: {
				type: String,
				default: 'Mensaje por defecto'
			}
		}
	}
</script>
<style>
	body {
		background-color: #eee;
	}
	.componente {
		background-color: #bada55;
	}
</style>