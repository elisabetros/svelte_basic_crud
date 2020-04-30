<script>
  import UserItem from "./UserItem.svelte";
  let users = [{ id: 1, name: "A" }, { id: 2, name: "B" }];
  let name = "";
  const addUser = e => {
    e.preventDefault();
    let id = Math.floor(Math.random() * 1000);
    users = [...users, { id, name }];
  };
  const deleteUser = e => {
    console.log(e.detail);
    users = users.filter(user => e.detail !== user);
  };
  const updateUser = e => {
    users = users;
  };
</script>

<style>
  .container {
    border: 1px solid black;
  }
</style>

<div class="container">
  {JSON.stringify(users)}
  <form on:submit={addUser}>
    <input type="text" placeholder="user name" bind:value={name} />
    <button>Add user</button>
  </form>
</div>

<div id="users">
  {#each users as user}
    <UserItem {user} on:deleteUser={deleteUser} on:updateUser={updateUser} />
  {/each}
</div>