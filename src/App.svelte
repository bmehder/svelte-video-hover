<script>
  import VideoPlayer from "./VideoPlayer.svelte";
  import Main from "./Main.svelte";
  import Footer from "./Footer.svelte";

  let y;
  // $: console.log(y);
  $: y > 400 ? (showFloat = true) : (showFloat = false);

  let showFloat = false;
</script>

<svelte:window bind:scrollY={y} />

<div class="header">
  <VideoPlayer {showFloat} />
</div>

<div class="navbar">
  <a href="a">Link</a>
  <a href="b">Link</a>
  <a href="c">Link</a>
  <a href="d" class="right">Link</a>
</div>

<Main />
<Footer />

<style>
  * {
    box-sizing: border-box;
  }

  /* Style the top navigation bar */
  .navbar {
    overflow: hidden;
    background-color: #333;
  }

  /* Style the navigation bar links */
  .navbar a {
    float: left;
    display: block;
    color: white;
    text-align: center;
    padding: 14px 20px;
    text-decoration: none;
  }

  /* Right-aligned link */
  .navbar a.right {
    float: right;
  }

  /* Change color on hover */
  .navbar a:hover {
    background-color: #ddd;
    color: black;
  }

  /* Responsive layout - when the screen is less than 400px wide, make the navigation links stack on top of each other instead of next to each other */
  @media screen and (max-width: 400px) {
    .navbar a {
      float: none;
      width: 100%;
    }
  }
</style>
