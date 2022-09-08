<script lang="ts">
	import {cover} from "../media/index";

	export let title: string;
	export let text: string;
</script>

<div class="h-screen flex items-center justify-center backdrop-blur-md">
  <div class="bg-blur h-full w-full fixed -z-10" />
  <img src={cover} alt="" class=" h-4/5 border-8" />
  
  <!-- <div class="fixed text-center">
    <div class="text-8xl font-bold text-white font-sans">Kartar Kaur</div>
    <p class="text-xl text-white font-light">Life in poetry</p>
  </div> -->
</div>

<style>
  .bg-blur {
    background-image: url(../media/cover.jpg);
    filter: blur(10px);
    -webkit-filter: blur(10px);
  }
  .text-blur {
    background-color: rgba(0, 0, 0, 0.4);
  }
</style>


