<script setup>
import { ref } from "vue";
import IconMenu from "./assets/images/IconMenu.vue";
import IconMenuClose from "./assets/images/IconMenuClose.vue";

let collapsed = ref(true);
const toggleMenu = () => {
  collapsed.value = !collapsed.value;
};
</script>

<template>
  <header class="pb-10 flex items-center justify-between">
    <img src="./assets/images/logo.svg" alt="logo" />
    <IconMenu @click="toggleMenu" class="cursor-pointer md:hidden" />
    <nav
      class="md:!block"
      :class="{
        hidden: collapsed,
        'not-collapsed overflow-y-scroll !block absolute right-0 top-0 bg-white max-w-xs w-full h-full z-10 ':
          !collapsed,
      }"
    >
      <ul class="md:flex md:gap-10 md:bg-transparent md:relative font-medium">
        <IconMenuClose
          class="ml-auto mt-10 mr-10 md:hidden"
          @click="toggleMenu"
        />
        <li class="link">Home</li>
        <li class="link">New</li>
        <li class="link">Popular</li>
        <li class="link">Trending</li>
        <li class="link">Categories</li>
      </ul>
    </nav>
  </header>
  <main>
    <div class="flex flex-col md:grid md:grid-cols-6 gap-5">
      <div class="col-span-4">
        <div>
          <img
            src="./assets/images/image-web-3-desktop.jpg"
            class="md:block hidden"
            alt=""
          />
          <img
            src="./assets/images/image-web-3-mobile.jpg"
            class="md:hidden block"
            alt=""
          />
        </div>
        <div
          class="flex flex-col gap-5 md:grid md:grid-cols-2 py-4 items-center"
        >
          <h3 class="capitalize text-slate-950 text-6xl font-bold">
            the bright future of web 3.0?
          </h3>
          <div>
            <p class="text-xl text-gray-500">
              We dive into the next evolution of the web that claims to put the
              power of the platforms back into the hands of the people. But is
              it really fulfilling its promise?
            </p>
            <button
              class="mt-8 bg-red-400 transition hover:bg-slate-950 text-white py-2 px-5 tracking-widest uppercase"
            >
              read more
            </button>
          </div>
        </div>
      </div>
      <div class="col-span-2 bg-slate-950 px-4 pt-10">
        <h4 class="text-amber-500 text-4xl font-bold mb-5">New</h4>
        <ul class="divide-y">
          <li>
            <h5 class="side-heading">Hydrogen VS Electric Cars</h5>
            <p>Will hydrogen-fueled cars ever catch up to EVs?</p>
          </li>
          <li>
            <h5 class="side-heading">The Downsides of Al Artistry</h5>
            <p>
              What are the possible adverse effects of on-demand Al image
              generation?
            </p>
          </li>
          <li>
            <h5 class="side-heading">Is VC Funding Drying Up?</h5>
            <p>
              Private funding by VC firms is down 50% YOY. We take a look at
              what that means
            </p>
          </li>
        </ul>
      </div>
    </div>
    <div
      class="flex flex-col md:grid md:grid-cols-6 gap-5 mt-16 md:items-center"
    >
      <div class="sub-topics">
        <div>
          <img src="./assets/images/image-retro-pcs.jpg" alt="retro-pcs" />
        </div>

        <div>
          <span class="sub-topics-num">01</span>
          <h5 class="sub-topics-heading">Reviving Retro PCs</h5>
          <p class="sub-topics-p">
            What happens when old PCs are given modern upgrades?
          </p>
        </div>
      </div>
      <div class="sub-topics">
        <div>
          <img src="./assets/images/image-top-laptops.jpg" alt="top-laptops" />
        </div>
        <div>
          <span class="sub-topics-num">02</span>
          <h5 class="sub-topics-heading">Top 10 Laptops of 2022</h5>
          <p class="sub-topics-p">
            Our best picks for various needs and budgets.
          </p>
        </div>
      </div>
      <div class="sub-topics">
        <div>
          <img
            src="./assets/images/image-gaming-growth.jpg"
            alt="gaming-growth"
          />
        </div>
        <div>
          <span class="sub-topics-num">03</span>
          <h5 class="sub-topics-heading">The Growth of Gaming</h5>
          <p class="sub-topics-p">
            How the pandemic has sparked fresh opportunities
          </p>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
ul > li.link {
  @apply text-gray-400 hover:text-red-400 cursor-pointer p-5 md:p-0;
}
ul > li:has(.side-heading) {
  @apply py-5;
}
.side-heading {
  @apply text-white text-xl font-medium mb-5 hover:text-amber-500 cursor-pointer;
}
.side-heading + p {
  @apply text-gray-300 text-lg;
}
.sub-topics {
  @apply col-span-2 flex gap-5 items-center;
}
.sub-topics > div:first-child {
  @apply max-w-[120px] w-full;
}
.sub-topics > div:first-child > img {
  @apply w-full;
}
.sub-topics-num {
  @apply text-gray-400 md:text-4xl font-bold text-2xl;
}
.sub-topics-heading {
  @apply text-slate-950 font-bold md:text-xl text-lg hover:text-red-400 cursor-pointer;
}
.sub-topics-p {
  @apply text-gray-500 md:text-lg text-sm;
}
</style>
