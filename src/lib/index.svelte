<script lang="ts">
	import { onMount } from 'svelte';

	export let global = true;
	export let opacity = 1;

	export let due_date: Date;
	export let days_deadline: number;

	let current_date = new Date();
	let utc1 = Date.UTC(due_date.getFullYear(), due_date.getMonth(), due_date.getDate());
	let utc2 = Date.UTC(current_date.getFullYear(), current_date.getMonth(), current_date.getDate());
	let days = Math.floor((utc2 - utc1) / (1000 * 60 * 60 * 24));


	if (days > 0) {
		let days_late = days_deadline - days;
		opacity = (days_late * 100) / days_deadline / 100;
		opacity = opacity < 0 ? 0 : opacity;
		opacity = opacity > 1 ? 1 : opacity;
	}

	onMount(() => {
		if (global) {
			document.body.style.opacity = opacity.toString();
		}
	});
</script>

{#if !global}
	<slot style="opacity: {opacity}" />
{/if}
