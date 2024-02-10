<script>
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();
    
    let type;
    let registrationDate;
    let capacity;
    // let bmw = false;
    // let tesla = false;
    // let vw = false;
    let cars = [];
    const hadleSubmit = () => {
        const car = {
            type,
            registrationDate,
            capacity,
            cars,
            id: Math.random(),
        }
        dispatch('addCar', car)
    }
</script>
<div>
	<form on:submit|preventDefault={hadleSubmit}>
        <!-- svelte-ignore a11y-label-has-associated-control -->
        <label>type</label>
		<!-- <input type="text" name="type" bind:value={type} placeholder="type"/> -->
        <select bind:value={type}>
            <option value="automobile">Automobile</option>
            <option value="trucker">Trucker</option>
            <option value="bajaj">Bajaj</option>
        </select>
        <!-- svelte-ignore a11y-label-has-associated-control -->
        <label>Registration date</label>
        <input type="date" name="registrationDate" bind:value={registrationDate} placeholder="Date"/>
        <!-- svelte-ignore a11y-label-has-associated-control -->
        <label>Capacity</label>
		<input type="number" name="capacity" bind:value={capacity} placeholder="capacity"/>
        <!-- svelte-ignore a11y-label-has-associated-control -->
        <label>Cars</label>
        <!-- <input type="checkbox" bind:checked={bmw}/>BMW<br/>
        <input type="checkbox" bind:checked={tesla}/>Tesla<br/>
        <input type="checkbox" bind:checked={vw}/>VW<br/> -->
        <input type="checkbox" bind:group={cars} value="bmw"/>BMW<br/>
        <input type="checkbox" bind:group={cars} value="tesla"/>Tesla<br/>
        <input type="checkbox" bind:group={cars} value="vw"/>VW<br/>
		<button>Add a car</button>
	</form>
</div>
<style></style>