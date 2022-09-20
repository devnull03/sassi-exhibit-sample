<script>
  import FullPageSlide from "../components/FullPageSlide.svelte";
  import FrontPage from "../components/FrontPage.svelte";
  import Slide from "../components/Slide.svelte";
  import { KartarKaur, AtmaSinghRai } from "../images/index";
  import SlideShow from "../components/SlideShow.svelte";
  import DoublePageSlide from "../components/DoublePageSlide.svelte";
  import Footer from "../components/Footer.svelte";

  const slides = [
    {
      title: "Kartar Kaur",
      text: `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt minus sapiente est modi praesentium nostrum blanditiis 
    totam dicta, 
    reprehenderit quod? Quasi sint aliquid totam nisi harum enim iure, officiis consequatur!`,
      images: [
        {
          src: KartarKaur,
          alt: "Kartar Kaur",
          link: "/",
        },
      ],
      flipped: false,
    },
    {
      title: "Atma Singh Rai",
      text: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt minus sapiente est modi praesentium nostrum blanditiis totam dicta, reprehenderit quod? Quasi sint aliquid totam nisi harum enim iure, officiis consequatur!",
      images: [
        {
          src: AtmaSinghRai,
          alt: "Atma Singh Rai",
          link: "/",
        },
      ],
      flipped: true,
    },
  ];
</script>

<div class="h-screen gap-11">
  <FrontPage />
  <Slide {...slides[0]} />
  <iframe
    title="map"
    style="border:0"
    loading="lazy"
    allowfullscreen
    class="rounded-lg border shadow-sm mt-5 w-full h-full"
    src="https://www.google.com/maps/embed/v1/place?q=place_id:ChIJ_Yz_Nb5KhFQRac_kYxebGAY&key=AIzaSyAFyX2Q-1_b6dJdj4NXGtTlATgG4WVSzXI"
  />
  <SlideShow />

  <Slide {...slides[1]} />

  <DoublePageSlide />

  <Footer />
</div>
