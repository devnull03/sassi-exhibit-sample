<script lang="ts">
  import {letter1, photo2} from "../images/index";

  export let flipped = false;
  export let strict = false;

  export let title = "Title";
  export let text = "";
  export let images = [
    {
      src: letter1,
      alt: "Image 1",
      link: "/",
    },
    {
      src: photo2,
      alt: "Image 2",
      link: "/",
    },
  ];

  let imageHeight: number;
  let infoDiv: HTMLDivElement;
  let imageDiv: HTMLDivElement;

  let windowWidth: number;
  let windowHeight: number;

  $: {
    imageHeight;
    if (infoDiv && windowWidth < 1024) {
      infoDiv.style.height = `${imageHeight * 2}px`;
      imageDiv.style.top = `${(windowHeight - imageHeight) / 2}px`;
    }
    if (infoDiv && strict) {
      infoDiv.style.width = `${windowWidth}px`;
      // infoDiv.style.height = `${windowHeight}px`;
    }
  }
</script>

<svelte:window bind:innerWidth={windowWidth} bind:innerHeight={windowHeight} />

<div
  class="flex snap-start {flipped
    ? 'flex-col-reverse lg:flex-row-reverse'
    : 'flex-col-reverse lg:flex-row'}"
>
  {#if imageHeight}
    <div
      class="flex flex-col z-20 lg:z-0 lg:sticky lg:top-0 lg:justify-center gap-5 p-20 lg:h-fit lg:w-1/2 mb-12 {flipped
        ? 'items-end text-right'
        : 'items-start'} text-white text-2xl font-light lg:text-black lg:text-base lg:font-normal"
      bind:this={infoDiv}
    >
      <h1 class="text-blur p-2 rounded-md lg:backdrop-blur-sm text-6xl pt-20">{title}</h1>
      <p class="text-blur p-2 rounded-md lg:backdrop-blur-sm text-3xl">
        {text}
      </p>
      <!-- <canvas class="bg-blue-600 rounded-lg border" /> -->
      <!-- <div class="hidden lg:flex">
        <slot />
      </div> -->
    </div>
  {/if}

  <div
    class="flex flex-col {flipped
      ? 'lg:ml-5'
      : 'lg:mr-5'} sticky lg:relative items-center justify-center h-full lg:w-1/2 hover:scale-105 shadow-lg hover:shadow-2xl cursor-pointer transition-all"
    bind:clientHeight={imageHeight}
    bind:this={imageDiv}
  >
    {#each images as image}
      <a href={image.link}> <img src={image.src} alt={image.alt} /> </a>
    {/each}
  </div>
</div>

<style>
  @media not (min-width: 1024px) {
    .text-blur {
      background-color: rgba(0, 0, 0, 0.4);
    }
  }
</style>

