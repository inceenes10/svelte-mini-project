<script>
    import { createEventDispatcher } from "svelte";

    let dispatch = createEventDispatcher();

    let name, beltColour, age, skills = [];
    const handleSubmit = () => {
        const person = {
            name, beltColour, age, skills, id: Math.random()
        };
        dispatch("addPerson", person);
    }
</script>


<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}/>
    <input type="number" placeholder="age" bind:value={age}/>
    <span>Skills</span>
    <input type="checkbox" bind:group={skills} value="coding"/>Coding<br />
    <input type="checkbox" bind:group={skills} value="running"/>Running<br />
    <input type="checkbox" bind:group={skills} value="sneaking"/>Sneaking<br />
    <span>Belt Colour:</span>
    <select bind:value={beltColour}>
        <option value="black">Black</option>
        <option value="orange">Orange</option>
        <option value="brown">Brown</option>
        <option value="white">White</option>
    </select>
    <button>Add Person</button>
</form>

<style>
</style>
