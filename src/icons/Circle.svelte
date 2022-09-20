<script lang="ts">
  export let active = false;

  let circleDiv: HTMLDivElement;

  $: {
    if (circleDiv) {
      if (active) {
        circleDiv.style.opacity = "1";
      } else {
        circleDiv.style.opacity = "0.5";
      }
    }
  }
</script>

<div class="h-8 w-8 rounded-full bg-[#D9D9D9]" bind:this={circleDiv} />
