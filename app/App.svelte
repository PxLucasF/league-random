<script>
  const champions = require('./assets/data/champions-pt_BR.json');

  let key = 0;
  function randomChampion() {
    key = Math.floor(Math.random() * champions.length);
  }
</script>

<page androidStatusBarBackground="#0cb3ce">
  <actionBar title="Random LoL Champions" />
  <flexboxLayout
    flexDirection="column"
		justifyContent="center"
    alignItems="center"
    backgroundImage="url('~/assets/img/loading/{champions[key].id}.jpg')"
  >
    <image src="~/assets/img/champion/{champions[key].id}.jpg" stretch="aspectFill" />
    <!-- svelte-ignore a11y-label-has-associated-control -->
    <label class="title" text="{champions[key].name}" />
    <!-- svelte-ignore a11y-label-has-associated-control -->
    <label class="subtitle" text="{champions[key].title}" />

    <button on:tap="{randomChampion}">
      <formattedString>
        <span class="fas" text="&#xf522;" />
        <span text=" Campeão aleatório" />
      </formattedString>
    </button>
  </flexboxLayout>
</page>

<style>
  flexboxLayout {
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }

  actionBar {
    background-color: #0bc4e2;
  }

  button {
    background-color: #0bc4e2;
    font-size: 18;
    padding: 0 16;
  }

  image {
    height: 120;
    width: 120;
    margin-bottom: 4;
    border-radius: 4;
  }

  .title {
    font-size: 32;
    font-weight: bold;
  }

  .subtitle {
    font-size: 18;
    margin-bottom: 16;
    text-transform: uppercase;
  }

  .title,
  .subtitle,
  button {
    font-family: 'BeaufortforLOL-Bold';
  }
</style>
