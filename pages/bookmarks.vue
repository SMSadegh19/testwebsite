<template>
  <main class="min-h-screen">
    <AppHeader class="mb-8" title="Bookmarks" :description="description" />

    <ul class="space-y-2">
      <li v-for="bookmark in bookmarks" :key="bookmark.id">
        <a
          :href="bookmark.url"
          target="_blank"
          rel="noopener noreferrer"
          class="flex items-center gap-3 hover:bg-gray-100 dark:hover:bg-white/10 p-2 rounded-lg -m-2 text-sm min-w-0"
        >
          <UAvatar
            :src="bookmark.url"
            :alt="bookmark.label"
            :ui="{ rounded: 'rounded-md' }"
          />
          <p class="truncate text-gray-700 dark:text-gray-200">
            {{ bookmark.label }}
          </p>
          <span class="flex-1"></span>
          <span class="text-xs font-medium text-gray-400 dark:text-gray-600">
            {{ bookmark.url }}
          </span>
        </a>
      </li>
    </ul>
  </main>
</template>

<script setup lang="ts">
const description =
  "Awesome things I've found on the internet. This page is still WIP, I want to add search like bmrks.com";

// SEO meta
useSeoMeta({
  title: "Bookmarks | Fayaz Ahmed",
  description,
});

// Static bookmark list
const bookmarks = [
  {
    id: 1,
    label: "Adam Wathan - Tailwind CSS Best Practice Patterns",
    url: "https://www.youtube.com/watch?v=J_7_mnFSLDg",
  },
  {
    id: 2,
    label: "Dicebear Awesome avatars",
    url: "https://www.dicebear.com/",
  },
  {
    id: 3,
    label: "Circuit design stock image",
    url: "https://images.unsplash.com/photo-1592659762303-90081d34b277",
  },
  {
    id: 4,
    label: "Beautiful Gradient Generator",
    url: "https://www.joshwcomeau.com/gradient-generator/",
  },
  {
    id: 5,
    label: "3D device mockups",
    url: "https://deviceframes.com/",
  },
  {
    id: 6,
    label: "Box shadow examples",
    url: "https://getcssscan.com/css-box-shadow-examples",
  },
  {
    id: 7,
    label: "Octopus Illustration",
    url: "https://refine.new/",
  },
  {
    id: 8,
    label: "Metalab agency",
    url: "https://www.metalab.com/",
  },
  {
    id: 9,
    label: "Tines - Beautiful landing page",
    url: "https://www.tines.com/product",
  },
  {
    id: 10,
    label: "SVG Spinners",
    url: "https://github.com/n3r4zzurr0/svg-spinners",
  },
  {
    id: 11,
    label: "ASCII Flow - Text based image drawing",
    url: "https://asciiflow.com/#/",
  },
  {
    id: 12,
    label: "REQRES Mock APIs for testing",
    url: "https://reqres.in/",
  },
  {
    id: 13,
    label: "Haikie - SVG background generator",
    url: "https://app.haikei.app/",
  },
  {
    id: 14,
    label: "IP API",
    url: "https://ipapi.is/",
  },
  {
    id: 15,
    label: "Rakko Tools",
    url: "https://en.rakko.tools/",
  },
];

// Safely extract host
// function getHost(url: string): string {
//   try {
//     const parsedUrl = new URL(url);
//     let host = parsedUrl.host;
//     return host.startsWith("www.") ? host.slice(4) : host;
//   } catch (e) {
//     console.warn("Invalid URL:", url);
//     return "invalid.url";
//   }
// }

// // Generate Clearbit thumbnail, or fallback
// function getThumbnail(url: string): string {
//   const host = getHost(url);
//   return host === "invalid.url"
//     ? "/fallback-logo.png" // Place a default logo in /public
//     : `https://logo.clearbit.com/${host}`;
// }
</script>
