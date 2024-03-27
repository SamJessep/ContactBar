<script>
  import GithubLink from "./components/GithubLink.svelte";
  import LinkedinLink from "./components/LinkedinLink.svelte";
  import TwitterLink from "./components/TwitterLink.svelte";
  import Themes from "./Themes"
  
  export let theme = "dark"
  export let links = {}
  export let height = "5vh"
  
  const selectedTheme = Themes[theme]
  </script>
  <div class="icon-container" style={"background-color:"+selectedTheme.background+"; height: "+height+";"}>
    {#if Object.keys(links).includes("twitter")}
      <TwitterLink color={selectedTheme.color} link={links.twitter}/>
    {/if}
    {#if Object.keys(links).includes("github")}
      <GithubLink color={selectedTheme.color} link={links.github}/>
    {/if}
    {#if Object.keys(links).includes("linkedin")}
      <LinkedinLink color={selectedTheme.color} link={links.linkedin}/>
    {/if}
  </div>
  
  <style>
    div.icon-container{
      max-height: 100%;
      width:100%;
      padding: 0.5rem 0;
      display: flex;
      justify-content: center;
    }

    :global(a){
      margin: 0 min(5%, 5px);
      display: contents;
      -webkit-tap-highlight-color: transparent;
    }
  </style>