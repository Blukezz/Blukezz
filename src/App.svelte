

<main>
  <div class="blob gradient" id="blob"></div>

  <div class="container-1">

    <div class="gradient pfp-container">
      <img class="pfp" src={profilepic} alt="a cool man"/>
    </div>

    <div class="text-container">
      <h1>Blukez.</h1>
      <p>dev & ui desginer ig</p>
      <div class="media-container">

        <a href="https://www.roblox.com/users/2774512260/profile" target="_blank" rel="noreferrer">
          <div class="roblox media-button">
            <img src={robloxicon} alt="roblox icon" style="width:1.5em; height:1.5em; opacity:0.25"/>
          </div>
        </a>

        <div class="discord media-button">
          <img class="discord-icon" src={changingcopyicon} alt="discord icon" style="width:1.5em; height:1.25em; opacity:0.25"/>
        </div>

      </div>
    </div>

  
  <div class="scroll-indicator">
    <p style="font-size: 16px; font-weight: 600; color:rgba(255,255,255, 0.35);">Scroll Down</p>
    <svg width="24" height="24" fill="none" class="icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M4.293 8.293a1 1 0 0 1 1.414 0L12 14.586l6.293-6.293a1 1 0 1 1 1.414 1.414l-7 7a1 1 0 0 1-1.414 0l-7-7a1 1 0 0 1 0-1.414Z" fill="rgba(255,255,255, 0.35)"/></svg>
  </div>

  </div>

  <div class="container-1">

  </div>
</main>

<style>
  @keyframes fadein {
    from { opacity: 0; }
    to { opacity: 1; }
  }

  @keyframes sizein {
    from { 
      scale: 0.75;
      opacity: 0;
     }

    to {
      scale: 1;
      opacity: 1;
    }
  }

  .blob {
    height: 50em;
    width: 50em;
    background: #FE48DD;
    background: linear-gradient(225deg, #FE48DD, #16A167);
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    transition: all 0.25s cubic-bezier(.5,1,.89,1);
    scale: 0;
  }
  
  .container-1 {
    margin: auto;
    max-width: 100vw;
    height: 100vh;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    position: relative;
  }
  .gradient {
    mask: radial-gradient(circle at 50% 50%, black 0%, transparent 50%);
  }
  .pfp-container {
    height: 35em;
    width: 35em;
    background: #FE48DD;
    background: linear-gradient(225deg, #FE48DD, #16A167);
    display: flex;
    align-items: center;
    justify-content: center;

    animation-name: sizein;
    animation-duration: 2s;
    animation-timing-function: cubic-bezier(.5,1,.89,1);
  }
  .pfp {
    height: 10em;
    width: 10em;
    border-radius: 50%;

    opacity: 0;
    animation-name: fadein;
    animation-duration: 2s;
    animation-timing-function: cubic-bezier(.5,1,.89,1);
    animation-delay: 0.5s;
    animation-fill-mode: forwards;
  }
  .text-container{
    width: 25em;
    display: flex;
    flex-direction: column;
    text-align: left;
  }
  p{
    line-height: 0;
    color: rgba(255, 255, 255, 0.69);


    opacity: 0;
    animation-name: fadein;
    animation-duration: 2s;
    animation-timing-function: cubic-bezier(.5,1,.89,1);
    animation-delay: 0.5s;
    animation-fill-mode: forwards;
  }
  h1 {
    line-height: 0;
    font-weight: bold;


    opacity: 0;
    animation-name: fadein;
    animation-duration: 2s;
    animation-timing-function: cubic-bezier(.5,1,.89,1);
    animation-delay: 0.25s;
    animation-fill-mode: forwards;
  }
  .media-container{
    padding-top: 0.5vw;
    display: flex;
    flex-direction: row;
    gap: 0.5vw;

    opacity: 0;
    animation-name: fadein;
    animation-duration: 2s;
    animation-timing-function: cubic-bezier(.5,1,.89,1);
    animation-delay: 1s;
    animation-fill-mode: forwards;
  }
  .media-button{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 3em;
    width: 3em;
    cursor: pointer;

    background: rgba(15, 15, 15, 0.5);
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    border: 1.5px solid rgba(30, 30, 30, 0.5);

    transition: all 0.25s cubic-bezier(.5,1,.89,1);
  }
  .media-button:hover {
    background: rgba(30, 30, 30, 0.2);
    filter: drop-shadow(#FFF);
    border-color: rgba(45, 45, 45, 0.1);
  }
  .scroll-indicator {
    position: absolute;
    bottom: 0;

    animation-name: fadein;
    animation-duration: 0.2s;
    animation-direction: reverse;
    animation-timeline: scroll(y);
  }
  .icon {
    opacity: 0;
    animation-name: sizein;
    animation-duration: 2s;
    animation-timing-function: cubic-bezier(.5,1,.89,1);
    animation-delay: 0.5s;
    animation-fill-mode: forwards;
  }
</style>

<script>
  import profilepic from './assets/blukez.jpg';
  import robloxicon from './assets/robloxicon.png';
  import discordicon from './assets/discordicon.png';
  import clipboardcheckicon from "./assets/clipboard_checkmark.png"

  var changingcopyicon = discordicon

  function onLoad() {
    let discord = document.body.querySelector(".discord")
    let discord_icon = document.body.querySelector(".discord-icon")

    let blob = document.getElementById("blob")
    let blobsize = blob.clientHeight / 2
    var mouseleft

    let profileblob = document.querySelector(".pfp-container")

    document.body.addEventListener("mouseleave", () => {
      mouseleft = true
      blob.animate(
        [{scale: 0, opacity: 0}],
        {duration: 250, iterations: 1, fill: 'forwards'}
      )
      profileblob.animate(
        [{opacity: 1}],
        {duration: 250, iterations: 1, fill: 'forwards'}
      )
    })

    document.body.addEventListener("mouseenter", () => {
      mouseleft = false
      blob.animate(
        [{scale: 1, opacity: 1}],
        {duration: 250, iterations: 1, fill: 'forwards'}
      )
      profileblob.animate(
        [{opacity: 0.69}],
        {duration: 250, iterations: 1, fill: 'forwards'}
      )
    })

    document.addEventListener("mousemove", (thing) => {
      if (mouseleft === false) {
        blob.style.left = `${thing.x - blobsize}px`
        blob.style.top = `${thing.y - blobsize}px`
      }
    })

    discord.addEventListener("mouseup", () => {
      discord_icon.animate(
        [{opacity: 0}],
        {duration: 200, iterations: 1, fill: 'forwards'}
      )

      setTimeout(function(){ 
        changingcopyicon = clipboardcheckicon
        navigator.clipboard.writeText("blukez");
        discord_icon.animate(
          [{opacity: 0.25}],
          {duration: 200, iterations: 1, fill: 'forwards'}
        )
      }, 200)


      setTimeout(function(){ 
        discord_icon.animate(
          [{opacity: 0}],
          {duration: 200, iterations: 1, fill: 'forwards'}
        )
      }, 800)

      setTimeout(function(){ 
        changingcopyicon = discordicon
        discord_icon.animate(
          [{opacity: 0.25}],
          {duration: 200, iterations: 1, fill: 'forwards'}
        )
      }, 1000)
    })
  }

  document.addEventListener("DOMContentLoaded", onLoad);
</script>