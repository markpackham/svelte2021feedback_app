<script>
	let firstName = 'Timmy';
	let lastName = 'Smith';
	let color = 'blue';
	let showText = false;
	let users = [
		{
			id: '1',
			name: 'Timmy'
		},
		{
			id: '2',
			name: 'Sara'
		},
		{
			id: '3',
			name: 'Bob'
		},
	]

	$: name = `${firstName} ${lastName}`;

	const toggle = () =>{
		color = color === 'blue' ? 'red' : 'blue'
		showText = !showText;
		users = [...users, {id: '4', name: 'David'}]
	}
</script>

<main>
	<h1 style="color: {color}">Hello {name}!</h1>
	{#if showText}
	<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae dolorum assumenda perspiciatis nisi repudiandae accusantium? Eaque magni fuga et earum. Quis ab tempore dignissimos est tempora veniam placeat voluptatibus non.</p>
	{:else}
	<p>No text</p>
	{/if}
	<button on:click={toggle}>Click</button>

	{#each users as user (user.id)}
		<h3>{user.name}</h3>
	{/each}
</main>

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