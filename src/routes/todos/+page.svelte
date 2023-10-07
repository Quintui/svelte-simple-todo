<script lang="ts">
	import Todo from '../../components/todo.svelte';
	import type { TodoType } from '../../types/todo';

	export let todos: TodoType[] = [
		{ isCompleted: false, title: 'First todo' },
		{ isCompleted: true, title: 'Second todo' }
	];

	let inputValue = '';

	const createTodo = () => {
		if (!inputValue) {
			return;
		}

		const newTodo: TodoType = {
			isCompleted: false,
			title: inputValue
		};
		todos = [...todos, newTodo];
		inputValue = '';
	};
</script>

<div class="space-y-3">
	<div class="w-full flex gap-3">
		<input
			value={inputValue}
			class="w-full p-2 border rounded"
			on:input={(e) => (inputValue = e.currentTarget.value)}
			placeholder="Create a New Todo"
			type="text"
		/>
		<button class="rounded bg-orange-500 text-white px-2" on:click={createTodo}>Create</button>
	</div>
	<ul>
		{#each todos as todo}
			<Todo {todo} />
		{/each}
	</ul>
</div>
