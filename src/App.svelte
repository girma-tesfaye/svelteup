<script>
	let name = "Girma";
	//let role = "Sr. Dev";
	let color = "pink";
	const changeColor = () => {
		color = "black";
	}
	// const inputColor = (event) => {
	// 	color = event.target.value;
	// }
	// const changeRole = () => {
	// 	role = "Sr. Full Stack dev"
	// }
	// const inputRole = (event) => {
	// 	role = event.target.value;
	// }
</script>

<main>
	<h1>Name: {name}!</h1>
	<p style="color: {color}">Color: {color}</p>
	<button style="color: {color}" on:click={changeColor}>Change color</button>
	<!-- <input type="text" on:input={inputRole} value={role}/> -->
	<input type="text" style="color: {color}" bind:value={color}/>
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