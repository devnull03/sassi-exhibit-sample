<script lang="ts">
  import Arrow from "../icons/Arrow.svelte";
  import { cover } from "../images/index";

  export let images = [
    {
      src: cover,
      alt: "Image 1",
      link: "/",
      active: false,
    },
    {
      src: cover,
      alt: "Image 2",
      link: "/",
      active: true,
    },
  ];

  $: currentImage = images.find((image) => image.active);
</script>

<div class="h-screen flex items-center">
  {#if currentImage}
    <img src={currentImage.src} alt={currentImage.alt} class="h-full w-full -z-10" />
  {/if}

  <div class="relative z-10 top-0 flex-grow">
    <Arrow flipped />
    <Arrow />
  </div>

</div>
