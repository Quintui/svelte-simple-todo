<script lang="ts">
	import type { TodoType } from '../types/todo';

	export let todo: TodoType;
</script>

<li class="p-3 flex items-center justify-between">
	<p class="flex text-slate-700">{todo.title}</p>
	<!-- Since I'm not sending changes to the db isCompleted will be handled like this. -->
	<button
		class={`p-2 rounded ${todo.isCompleted ? 'bg-green-400' : 'bg-blue-300'}`}
		on:click={() => (todo.isCompleted = !todo.isCompleted)}
		>{todo.isCompleted ? 'Completed' : 'Not Completed'}</button
	>
</li>
