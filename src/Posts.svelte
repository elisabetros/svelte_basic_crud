<script>
  let ajPosts = [
    { id: 1, "friendID": 1, title: "POst one", body: "Body one" },
    { id: 2, "friendID": 2, title: "POst two", body: "Body two" },
    { id: 3, "friendID": 1, title: "POst three", body: "Body 3" }
  ];
</script>

<style>
  .post {
    border: 1px solid purple;
  }
  .posts {
    display: grid;
    grid-gap: 0.5rem;
  }
</style>

<section class="posts">
  <h1>Posts</h1>

  {#each ajPosts as jPost}
    <div class="post">
      <div>{jPost.title}</div>
      <div>{jPost.body}</div>

    </div>
  {/each}
</section>