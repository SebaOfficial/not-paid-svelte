<script lang="ts">
	import NotPaid from '$lib/index.js';

	let due_date: string;
	let days_deadline: number;

	let show_not_paid = false;

	const createNotPaidElement = () => show_not_paid = true;
</script>


{#if show_not_paid}
	<NotPaid due_date={new Date(due_date)} days_deadline={days_deadline} />
{/if}

<h1>Demo</h1>

<form>
	<label for="due-date">Select the Due Date:</label>
	<input type="date" id="due-date" bind:value={due_date} required>

	<br>

	<label for="days-deadline">Select How many days till the website is vanished:</label>
	<input type="number" id="days-deadline" bind:value={days_deadline} required>

	<br>
	
	<button type="submit" on:click={createNotPaidElement}>Create NotPaid Element</button>
</form>
