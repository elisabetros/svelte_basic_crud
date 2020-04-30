<script>
  import { createEventDispatcher } from "svelte";
  let dispatch = createEventDispatcher();
  export let user = {
    id: 0,
    name: ""
  };
  const deleteUser = () => {
    dispatch("deleteUser", user);
  };
  const updateUser = () => {
    dispatch("updateUser");
  };
</script>

<style>
  .user {
    background-color: azure;
  }
</style>

<div class="user">
  <div>ID{user.id}</div>
  <div>Name{user.name}</div>
  <input type="text" bind:value={user.name} on:input={updateUser} />
  <button on:click={deleteUser}>🚮</button>
</div>