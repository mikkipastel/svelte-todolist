<script>
	export let input;
	export let output = "";

	function handleClick() {
		output = input;
	}
</script>

<input bind:value={input} placeholder="enter something">
<button on:click={handleClick}>
	Add
</button>
<h1>{output}</h1>