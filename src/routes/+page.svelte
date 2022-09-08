<script>
  import FullPageSlide from "../components/FullPageSlide.svelte";
  import FrontPage from "../components/FrontPage.svelte";
  import Slide from "../components/Slide.svelte";
  import { photo1, photo2, coverCont } from "../media/index";

  const slides = [
    {
      title: "Title",
      text: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt minus sapiente est modi praesentium nostrum blanditiis totam dicta, reprehenderit quod? Quasi sint aliquid totam nisi harum enim iure, officiis consequatur!",
      images: [
        {
          src: photo1,
          alt: "Image 1",
          link: "/",
        },
      ],
      flipped: false,
    },
    {
      title: "Title",
      text: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt minus sapiente est modi praesentium nostrum blanditiis totam dicta, reprehenderit quod? Quasi sint aliquid totam nisi harum enim iure, officiis consequatur!",
      images: [
        {
          src: photo2,
          alt: "Image 2",
          link: "/",
        },
      ],
      flipped: true,
    },
  ];
</script>

<div class="h-screen gap-11">
  <FrontPage />
  {#each slides as slide}
    <Slide {...slide}>
      <!-- <canvas class="bg-blue-600 rounded-lg border" /> -->
      <iframe
        title="map"
        style="border:0"
        loading="lazy"
        allowfullscreen
        class="rounded-lg border shadow-sm mt-5 w-full h-full"
        src="https://www.google.com/maps/embed/v1/place?q=place_id:ChIJ_Yz_Nb5KhFQRac_kYxebGAY&key=AIzaSyAFyX2Q-1_b6dJdj4NXGtTlATgG4WVSzXI"
      />
    </Slide>
  {/each}
  <FullPageSlide title="title" text="hmm" />
  <!-- {#each slides as slide} -->
    <Slide images={[
      {
        src: coverCont,
        alt: "Image 1",
        link: "/",
      },
    ]} >
      <iframe
        title="map"
        style="border:0"
        loading="lazy"
        allowfullscreen
        class="rounded-lg border shadow-sm mt-5"
        src="https://www.google.com/maps/embed/v1/place?q=place_id:ChIJ_Yz_Nb5KhFQRac_kYxebGAY&key=AIzaSyAFyX2Q-1_b6dJdj4NXGtTlATgG4WVSzXI"
      />
    </Slide>
  <!-- {/each} -->
</div>
