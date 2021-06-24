<script>
  import '@glidejs/glide/dist/css/glide.core.min.css';
  import { onMount } from 'svelte';
  import Glide from '@glidejs/glide';
  import * as uuid from 'uuid';

  export let carouselId = `carousel-${uuid.v4()}`;
  let slidesContainerEl;
  let slidesSize;
  onMount(() => {
    slidesSize = slidesContainerEl.children.length;
    new Glide(`#${carouselId}`).mount();
  });
</script>

<div class="glide" id={carouselId}>
  <div class="glide__track" data-glide-el="track">
    <ul class="glide__slides" bind:this={slidesContainerEl}>
      <slot />
    </ul>
  </div>

  <div class="glide__bullets" data-glide-el="controls[nav]">
    {#each Array(slidesSize) as _, i}
      <button class="glide__bullet" data-glide-dir={`=${i}`} />
    {/each}
  </div>
</div>

<style>
  .glide__bullets {
    position: absolute;
    bottom: 0.3em;
    width: 100%;
    display: flex;
    justify-content: center;
  }
  .glide__bullet {
    margin: 1em;
  }
</style>
