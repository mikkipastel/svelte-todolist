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

<h1>TODO LIST</h1>

<input bind:value={input} placeholder="enter something">
<button on:click={addTodo}>
    Add
</button>

{#each todoList as todo}
    <div class="flex flex-row">
        <input class="place-self-center" type=checkbox bind:checked={todo.done}>
        <p class="mx-4">
            {#if todo.done}
                <strike>{todo.text}</strike>
            {:else}
                {todo.text}
            {/if}
        </p>
    </div>
{/each}