<script>
  import FriendThumbnail from "./FriendThumbnail.svelte";
  let ajFriends = [
    { id: 1, name: "A", status: 1 },
    { id: 2, name: "B", status: 0 },
    { id: 3, name: "C", status: 1 }
  ];
</script>

<style>
  /* .friend {
    display: grid;
    justify-content: center;
    align-content: center;
    width: 2rem;
    height: 2rem;
    border: 1px solid black;
    border-radius: 50%;
  } */
  .friends {
    display: grid;
    grid-gap: 0.5rem;
  }
</style>

<section class="friends">
  <h1>Friends list</h1>
  {#each ajFriends as jFriend}
    <FriendThumbnail {...jFriend}/>
  {/each}
</section>