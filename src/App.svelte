<script>
	import AddCarForm from "./AddCarForm.svelte";
import Modal from "./Modal.svelte";
	let name = "Girma";
	let showModal = false;
	const toggleModal = () => {
		showModal = !showModal
	}
	//let role = "Sr. Dev";
	// let color = "pink";
	// let size = "Big";
	// const changeColor = () => {
	// 	color = "black";
	// }
	// $: description = `${color} and the size is ${size}`
	// $: {
	// 	console.log(name);
	// 	console.log(description);
	// }
	// const inputColor = (event) => {
	// 	color = event.target.value;
	// }
	// const changeRole = () => {
	// 	role = "Sr. Full Stack dev"
	// }
	// const inputRole = (event) => {
	// 	role = event.target.value;
	// }

	let cars = [
		{
			"color": "purple",
			"type": "minivan",
			"registration": new Date('2017-01-03'),
			"capacity": 7,
			"id": 2
		},
		{
			"color": "red",
			"type": "station wagon",
			"registration": new Date('2018-03-03'),
			"capacity": 5,
			"id": 4
		},
		{
			"color": "black",
			"type": "highchi",
			"registration": new Date('2019-05-03'),
			"capacity": 3,
			"id": 6
		}
	]
	const deleteCar = (capacity) => {
		cars = cars.filter((car) => car.capacity != capacity 
	)}
	const addCar = (e) => {
		const newCar =  e.detail;
		cars = [newCar, ...cars]
	}
</script>

<Modal 
	{showModal} 
	on:click={toggleModal}
>
	<AddCarForm on:addCar={addCar}/>
</Modal>
<main>
	<button on:click|once={toggleModal}>Open Modal</button>
	<h1>Name: {name}!</h1>
	<!-- <p>{description}</p> -->
	<!-- <button style="color: {color}" on:click={changeColor}>Change color</button> -->
	<!-- <input type="text" on:input={inputRole} value={role}/> -->
	<!-- <input type="text" bind:value={color}/> -->
	<!-- <input type="text" bind:value={size}/> -->
	{#each cars as car (car.registration)}
		<div>
			<h4>{car.type}</h4>
			{#if car.capacity === 3}
				<p>This is highch</p>
			{:else if car.capacity === 5 }
				<p>This is minivan</p>
			{/if}
			<p>{car.color}</p>
			<p>Registration date: {car.registration}</p>
			<p>{car.capacity}</p>
			<button on:click={()=> deleteCar(car.capacity)}>Delete</button>
		</div>
	{:else}
	<p>There is no car listed here</p>
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