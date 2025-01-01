<script lang="ts">
	import type { Task } from '../types';
	let {
		tasks
	}: {
		tasks: Task[];
	} = $props();
</script>

<section>
	{#each tasks as task}
		<article>
			{task.title}
		</article>
	{/each}
</section>
