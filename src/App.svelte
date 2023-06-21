<script>
	import Todos from "./components/Todos.svelte"

	export let name;
	let flag
	const toggleName = () => {
		if(flag) name = "World"
		else name = "Svelte"
		flag = !flag
	}

	let todos = [
		{ id: 1, name: "Create a Svelte starter app", completed: true },
		{ id: 2, name: "Create your first component", completed: true },
		{ id: 3, name: "Complete the rest of the tutorial", completed: false },
	];
</script>

<main>
	<h1>Hello {name}!</h1>
	<button on:click="{toggleName}">ToggleName</button>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
</main>

<Todos {todos} />

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>