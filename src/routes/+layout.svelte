<script>
  import { MutexObserver } from "$lib/stores/nostrocket_state/mutex";
  import {
    Column,
    Content,
    Grid,
    Row,
    Tile,
    breakpointObserver,
  } from "carbon-components-svelte";
  import "carbon-components-svelte/css/g100.css";
  import Header from "./Header.svelte";
  import "./styles.css";
  let size = breakpointObserver();
  $: {
    console.log("breakpoint: " + $size);
  }
</script>

<svelte:head>
  <title>Nostrocket</title>
</svelte:head>

<Header />

<Content>
  <Grid fullWidth>
    <Row>
      <Column>
        <slot />
      </Column>
    </Row>
    <br />
    <Row condensed>
      <div
        style="width:100%;height:40px;overflow:hidden;position:relative;left:0;bottom:0;text-align:right;padding-right:1%;"
      >
        <Tile style="width:100%;">
          <a href="https://satellite.earth/n/nostrocket">/n/nostrocket</a> | <a href="https://github.com/nostrocket">GitHub</a> | <a href="https://t.me/nostrocket">Telegram Group</a>
        </Tile>
      </div>
    </Row>
  </Grid>
</Content>
