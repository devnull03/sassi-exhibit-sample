<script lang="ts">
  import Circle from "../icons/Circle.svelte";
  import Arrow from "../icons/Arrow.svelte";
  import { cover, FamilyFullScreen } from "../images/index";

  export let images = [
    {
      src: cover,
      alt: "Image 1",
      link: "/",
      active: true,
    },
    {
      src: FamilyFullScreen,
      alt: "Image 2",
      link: "/",
      active: false,
    },
  ];

  $: currentImage = images.filter((image) => image.active)[0];
  let mainDiv: HTMLDivElement;
  const refresh = () => {
    currentImage = images.filter((image) => image.active)[0];
    mainDiv.style.backgroundImage = `url(${currentImage.src})`;
    console.log(currentImage);
  };
  const nextImage = () => {
    const currentIndex = images.indexOf(currentImage);
    const nextIndex = currentIndex + 1;
    if (nextIndex < images.length) {
      images[currentIndex].active = false;
      images[nextIndex].active = true;
    } else {
      images[currentIndex].active = false;
      images[0].active = true;
    }
    refresh();
  };
  const prevImage = () => {
    const currentIndex = images.indexOf(currentImage);
    const prevIndex = currentIndex - 1;
    if (prevIndex >= 0) {
      images[currentIndex].active = false;
      images[prevIndex].active = true;
    } else {
      images[currentIndex].active = false;
      images[images.length - 1].active = true;
    }
    refresh();
  };
</script>

<div
  class="h-screen flex items-center relative"
  bind:this={mainDiv}
  style="background-image: url({currentImage.src});"
>
  <div class="flex flex-row justify-between w-full px-10">
    <Arrow flipped on:click={prevImage} />
    <Arrow on:click={nextImage} />
  </div>
  <div class="absolute bottom-0 flex flex-row w-full justify-center pb-5 gap-3">
    {#each images as image}
      <Circle active={image.active} />
    {/each}
  </div>
</div>
