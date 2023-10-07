<script>
	import '../app.css';
</script>

<div class="w-screen h-screen flex justify-center items-center">
	<div class="p-6 min-h-[460px] w-full max-w-[400px] bg-white space-y-6 rounded-xl shadow-xl">
		<header>
			<nav class="flex gap-3 w-full justify-center">
				<a class="p-1 bg-blue-50 rounded-md text-slate-600" href="/">Home</a>
				<a class="p-1 bg-blue-50 rounded-md text-slate-600" href="/todos">Create Todos</a>
			</nav>
		</header>
		<hr />
		<main class="h-full">
			<slot />
		</main>
	</div>
</div>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.blue.300);
	}
</style>
