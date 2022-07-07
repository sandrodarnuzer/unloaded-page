<script lang="ts">
  import Firefox from "./components/Firefox.svelte";
  import Chrome from "./components/Chrome.svelte";
  import Safari from "./components/Safari.svelte";

  let userAgent = navigator.userAgent;
  let component;

  if (userAgent.match(/chrome|chromium|crios/i)) {
    component = Chrome;
  } else if (userAgent.match(/firefox|fxios/i)) {
    component = Firefox;
  } else if (userAgent.match(/safari/i)) {
    component = Safari;
  } else if (userAgent.match(/opr\//i)) {
    component = "opera";
  } else if (userAgent.match(/edg/i)) {
    component = "edge";
  } else {
    component = "No browser detection";
  }
</script>

<svelte:head>
  <title>{window.location.host}</title>
</svelte:head>
<svelte:component this={component} />
