<script lang="ts">
	let newTask = $state('');
	let {
		addTask
	}: {
		addTask: (newTask: string) => void;
	} = $props();

	function formSubmitted(e: SubmitEvent) {
		e.preventDefault();
		addTask(newTask);
		newTask = '';
	}
</script>

<form onsubmit={formSubmitted}>
	<label>
		Task
    <!-- svelte-ignore a11y_autofocus -->
		<input name="newTask" bind:value={newTask} autofocus/>
	</label>
	<div class="button-container">
		<button>Add</button>
	</div>
</form>

<style>
	form {
		margin-bottom: 1rem;
	}
	.button-container {
		display: flex;
		justify-content: end;
	}
</style>
