<script lang="ts">
  const base = "http://localhost:";
  export const mappings = [
    {
      id: "pihole",
      route: `${base}81`,
      imageLink: "assets/pihole.svg",
      name: "Pihole",
    },
    {
      id: "plex",
      route: `${base}32400/web`,
      imageLink: "assets/plex.svg",
      name: "Plex",
    },
    {
      id: "radarr",
      route: `${base}7878`,
      imageLink: "assets/radarr.svg",
      name: "Radarr",
    },
    {
      id: "jackett",
      route: `${base}9117`,
      imageLink: "assets/jackett.svg",
      name: "Jackett",
    },
    {
      id: "sonarr",
      route: `${base}8989`,
      imageLink: "assets/sonarr.svg",
      name: "Sonarr",
    },
    {
      id: "deluge",
      route: `${base}8112`,
      imageLink: "assets/deluge.svg",
      name: "Deluge",
    },
  ];
</script>

<main>
  <h1 class="top-heading">Welcome to your Home-Docker</h1>
  <div class="grid">
    {#each mappings as { id, route, imageLink, name }}
      <div class="card">
        <h1>{name}</h1>
        <a href={route}>
          <img class="image" src={imageLink} alt={id} />
        </a>
      </div>
    {/each}
  </div>
</main>

<style>
  :root {
    --background: #232931;
    --standout: #3d4750;
    --contrast: #4ecca3;
    --notSelected: #393e46;
    --whiteish: #eeeeee;
  }
  main {
    background: var(--background);
    text-align: center;
    display: flex;
    flex-direction: column;
    max-height: 100%;
    overflow: auto;
  }

  .top-heading {
    color: var(--contrast);
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
    height: 80%;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 1fr);
    column-gap: 10px;
    row-gap: 15px;
  }

  .image {
    height: 100%;
    width: 100%;
  }
  .card {
    background: var(--whiteish);
    border-radius: 5%;
    display: flex;
    flex-direction: column;
  }
  .card:hover h1 {
    color: var(--contrast);
  }
</style>
