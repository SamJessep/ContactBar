<script>
  import GithubLink from "./components/GithubLink.svelte";
  import LinkedinLink from "./components/LinkedinLink.svelte";
  import TwitterLink from "./components/TwitterLink.svelte";
  import Themes from "./Themes"
  
  export let theme = "dark"
  export let links = {}
  
  const selectedTheme = Themes[theme]
  </script>
  <aside style={"background-color:"+selectedTheme.background+";"}>
    {#if Object.keys(links).includes("twitter")}
      <TwitterLink color={selectedTheme.color} link={links.twitter}/>
    {/if}
    {#if Object.keys(links).includes("github")}
      <GithubLink color={selectedTheme.color} link={links.github}/>
    {/if}
    {#if Object.keys(links).includes("linkedin")}
      <LinkedinLink color={selectedTheme.color} link={links.linkedin}/>
    {/if}
  </aside>
  
  <style>
    aside{
      width:100%;
      height: 65px;
      display: flex;
      justify-content: center;
    }
  </style>