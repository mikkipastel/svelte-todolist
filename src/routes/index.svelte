<script>
    export let input = "";

    let todoList = [];

    function addTodo() {
        let item = {
            done: false,
            text: input,
        };
        todoList = [...todoList, item];
        console.log(todoList);
        input = '';
    }
</script>

<div class="mx-24 my-24">
    <h1 class="text-2xl">TODO LIST</h1>

    <input class="mt-8 border-solid border-2" bind:value={input} placeholder="enter something">
    <button class="mx-4" on:click={addTodo}>
        Add
    </button>

    {#each todoList as todo}
        <div class="flex flex-row mt-2">
            <input class="place-self-center rounded-lg" type=checkbox bind:checked={todo.done}>
            <p class="mx-4">
                {#if todo.done}
                    <strike>{todo.text}</strike>
                {:else}
                    {todo.text}
                {/if}
            </p>
        </div>
    {/each}
</div>
