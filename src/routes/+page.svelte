<script lang="ts">
	import TasksForm from '../components/tasks-form.svelte';
	import TasksList from '../components/tasks-list.svelte';
	import type { Task } from '../types';
	let message = 'Tasks App';
	let tasks = $state<Task[]>([]);

	function addTask(newTask: string) {
		tasks.push({
			id: crypto.randomUUID(),
			title: newTask,
			done: false
		});
	}
</script>

<main>
	<h1>{message}</h1>
	<TasksForm {addTask} />
	<TasksList {tasks} />
</main>

<style>
	main {
		margin: 1rem auto;
		max-width: 800px;
	}
</style>
