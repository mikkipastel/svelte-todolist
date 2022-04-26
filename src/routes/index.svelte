<script>
	export let name = '';
</script>

<input bind:value={name} placeholder="enter something">
<h1>{name}</h1>