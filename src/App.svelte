<script>
  import profilepic from './assets/blukez.jpg';
  import githubicon from './assets/githubicon.png';
  import discordicon from './assets/discordicon.png';
</script>

<main>
  <div class="container-1">

    <div class="gradient pfp-container">
      <img class="pfp" src={profilepic} alt="a cool man"/>
    </div>

    <div class="text-container">
      <h1 class="pfp-title">Blukez</h1>
      <p class="pfp-description">A very pro</p>
      <div class="media-container">

        <a href="https://github.com" target="_blank" rel="noreferrer">
          <div class="github media-button">
            <img src={githubicon} alt="github icon" style="width:1.5vw; height:1.5vw; opacity:0.25"/>
          </div>
        </a>

        <a href="https://discord.com" target="_blank" rel="noreferrer">
          <div class="discord media-button">
            <img src={discordicon} alt="discord icon" style="width:1.5vw; height:1.25vw; opacity:0.25"/>
          </div>
        </a>

      </div>
    </div>
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
  
  .container-1 {
    margin: auto;
    max-width: 100vw;
    height: 45vw;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
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
    width: 35em;
    display: flex;
    flex-direction: column;
    text-align: left;
  }
  p{
    line-height: 0;


    opacity: 0;
    animation-name: fadein;
    animation-duration: 2s;
    animation-timing-function: cubic-bezier(.5,1,.89,1);
    animation-delay: 0.5s;
    animation-fill-mode: forwards;
  }
  h1 {
    line-height: 0;


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

    background: #151515;
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    border: 1.5px solid #1e1e1e;

    transition: all 0.25s cubic-bezier(.5,1,.89,1);
  }

  .media-button:hover {
    background: #1e1e1e;
    filter: drop-shadow(#FFF);
    border-color: #2d2d2d;
  }
</style>
