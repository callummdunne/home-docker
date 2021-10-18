<script lang="ts">
  const base = "http://localhost:";
  export const mappings = [
    { id: "pihole", route: `${base}81`, imageLink: "assets/pihole.svg" },
    { id: "plex", route: `${base}32400/web`, imageLink: "assets/plex.svg" },
    { id: "radarr", route: `${base}7878`, imageLink: "assets/radarr.svg" },
    { id: "jackett", route: `${base}9117`, imageLink: "assets/jackett.svg" },
    { id: "sonarr", route: `${base}8989`, imageLink: "assets/sonarr.svg" },
    { id: "deluge", route: `${base}8112`, imageLink: "assets/deluge.svg" },
  ];
</script>

<main>
  <h1>Welcome to your Home-Docker</h1>
  <div class="grid">
    {#each mappings as { id, route, imageLink }}
      <div />
      <img src={imageLink} alt={id} />
      <!-- <iframe src={route} title={id} /> -->
    {/each}
  </div>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
    height: 100%;
    width: 100%;
    display: flex;
    flex-direction: column;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }

  .grid {
    height: 100%;
    display: grid;
    grid-template-columns: auto auto auto;
    grid-template-rows: auto auto;
    column-gap: 10px;
    row-gap: 15px;
  }
</style>
