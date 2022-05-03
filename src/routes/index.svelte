<script>
    export let input = "";

    let todoList = [];

    function addTodo() {
        todoList = [...todoList, input];
        console.log(todoList);
        input = '';
    }
</script>

<h1>TODO LIST</h1>

<input bind:value={input} placeholder="enter something">
<button on:click={addTodo}>
    Add
</button>

{#each todoList as todo}
    <div class="flex flex-row">
        <input class="place-self-center" type=checkbox>
        <p class="mx-4">{todo}</p>
    </div>
{/each}