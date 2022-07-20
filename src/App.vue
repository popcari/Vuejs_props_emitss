<template>
	<form >
		<label>To do by Vue3</label>
		<hr/>
	</form>
		<div class="submit-area">
			<input v-model="newTodo" type="text" placeholder="Add new">
			<button @click.prevent="addNew">Submit</button>
		</div>
		<ul>
			<li v-for="(todo, index) in todos" :key="todo.id" class="todo">
			<h3 :class="{done:todo.done}" @click="toggleDone(todo)">{{todo.content}} </h3>
			<button @click="removeTodo(index)">remove</button>
		</li>
		</ul>

</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
// import { tSModuleDeclaration } from '@babel/types';
import {ref} from 'vue'

export default {
	name: "App",
	components: {
	
	},
	setup(){
		function addNew(){
			todos.value.push({
				id: Date.now(),
				done: false,
				content: newTodo.value,
			});
			newTodo.value = "";
		}
		const newTodo = ref("");
		const todos = ref([]);

		function toggleDone(todo){
			todo.done = !todo.done;
		}
		function removeTodo(index){
			todos.value.splice(index, 1)
		}
		return{
			addNew,  
			newTodo,
			todos,
			toggleDone,
			removeTodo
			}}
	}
</script>

<style>
form{
	display:flex;
	align-items:center;
	justify-content:center;
	flex-direction:column;
}
.submit-area{
display: flex;
justify-content: space-around;
}
input{
	padding: 10px 10px;
	width: 60%;
}

h3{
width: 60vw;
	/* background-color: rgb(238, 203, 157); */
	color: rgb(0, 0, 0);
}
li{
	list-style-type:decimal;
}
.done{
	text-decoration: line-through;
}
.todo{
	cursor: pointer;
}
</style>
