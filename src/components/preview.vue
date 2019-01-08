		<span v-html="myHtml"></span>
		<div v-if="showName">
			<p>{{ user.firstName }}</p>
		</div>
		<div v-else="showName">
			<p>nada perro</p>
		</div>
		<hr>
		<ul>
			<li v-for="task in tasks" > 
				{{ task.title }} 
			</li>
		</ul>
		<hr>
		<input type="text" v-model="user.firstName">
		<button 
			type="button" 
			v-on:click="saludar(user.firstName)"
		>
			click me
		</button>
		<hr>
		<input type="text" v-on:keyup.enter="typedEnter">