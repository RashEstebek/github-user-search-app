<script>
  import { onMount } from "svelte";
  import User from "./components/User.svelte";
  import UserSearch from "./components/UserSearch.svelte";
  let users;

  onMount(() => {
    githubUsers();
  });

  const githubUsers = () => {
    fetch("https://api.github.com/users")
      .then(res => res.json())
      .then(data => {
        users = data;
      });
  };
</script>

<main class="main">
  <nav class="nav">
    <span class="devfinder">devfinder</span>
    <span class="light-dark">LIGHT</span>
  </nav>
  <UserSearch />
  <article class="article">
    <section class="section">
      <picture>
        <img src="../public/Oval.png" alt="Octocat">
      </picture>
      <div>
        <p>The Octocat</p>
        <span>@octocat</span>
        <small>Joined 25 Jan 2011</small>
        <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Donec odio. Quisque volutpat mattis eros.</p>
      </div>
    </section>

    <section class="followers">
      <div class="sub">
        <div class="words">
          <p>Repos</p>
          <p>Followers</p>
          <p>Following</p>
        </div>
  
        <div class="numbers">
          <p>8</p>
          <p>3938</p>
          <p>9</p>
        </div>
      </div>
      
    </section>
    

  </article>
</main>

<style>
</style>
