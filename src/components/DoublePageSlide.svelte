<script lang="ts">
  import { FamilyFullScreen } from "../images/index";
  export let cover_image = FamilyFullScreen;

  let imageHeight: number;
  let infoDiv: HTMLDivElement;
  let imageDiv: HTMLDivElement;

  let windowWidth: number;
  let windowHeight: number;

  $: {
    imageHeight;
    if (infoDiv && windowWidth < 1024) {
      infoDiv.style.height = `${imageHeight * 2}px`;
//       imageDiv.style.top = `${(windowHeight - imageHeight) / 2}px`;
    }
  }


</script>


<svelte:window bind:innerWidth={windowWidth} bind:innerHeight={windowHeight} />

<div class="flex flex-col items-center justify-center">
  <div class="h-screen sticky top-0" bind:clientHeight={imageHeight} bind:this={imageDiv}>
    <img src={cover_image} alt="" />
  </div>

  <div class="z-20 flex justify-center p-28 text-6xl" bind:this={infoDiv}>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima tempore
      corrupti, iure maiores aut et quas fugiat natus quasi dolorum nesciunt
      velit, cumque veritatis asperiores quod perferendis ipsum eligendi
      delectus!
    </p>
  </div>
</div>
