<script>
  export let showFloat = false;

  let videoCont;
  let videoPlayer;

  const hideSmallPlayer = () => {
    videoCont.classList.remove("float");
    videoPlayer.classList.remove("sm-player");
  };
</script>

<div
  id="video-cont"
  class="video-cont"
  class:float={showFloat}
  bind:this={videoCont}>
  {#if showFloat}
    <div id="close-icon" on:click={hideSmallPlayer}>X</div>
  {/if}

  <video
    class="vid-player controls"
    class:sm-player={showFloat}
    bind:this={videoPlayer}>
    <track kind="captions" />
    <source
      src="https://media.istockphoto.com/videos/timelapse-aerial-view-of-chicago-skyline-cityscape-looking-south-loop-video-id1209608377"
      type="video/webm" />
    <source
      src="https://media.istockphoto.com/videos/timelapse-aerial-view-of-chicago-skyline-cityscape-looking-south-loop-video-id1209608377"
      type="video/mp4" />
    Sorry, your browser does not support videos.
  </video>
</div>

<style>
  .video-cont {
    max-width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    z-index: 10;
  }

  #close-icon {
    display: block;
    position: absolute;
    font-size: 1rem;
    color: #fff;
    font-weight: 800;
    top: 1%;
    right: 3%;
    cursor: pointer;
  }

  #close-icon:active {
    color: red;
  }

  @keyframes fade {
    100% {
      opacity: 1;
    }
  }

  @keyframes enterR {
    0% {
      right: -40%;
    }
  }

  .vid-player {
    width: 100%;
  }

  .float {
    width: 290px;
    height: 200px;
    box-shadow: 0 0 7px darkgray;
    background-color: #000;
    position: fixed;
    bottom: 1%;
    right: 1%;
    animation: enterR 0.2s ease-in-out;
  }

  .sm-player {
    width: 270px;
    height: 160px;
  }
</style>
