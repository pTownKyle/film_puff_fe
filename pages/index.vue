<template>
  <main class="flex flex-col w-full h-full justify-evenly items-center mt-3">
    <div class="flex flex-col items-center justify-center">
      <p class="mb-9">Film Puff Logo</p>
      <p class="text-justify mb-3">
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Veritatis nam
        ex sit nobis commodi obcaecati, maiores ab dolorem blanditiis
        exercitationem amet aperiam temporibus modi quae excepturi fugit aliquam
        accusamus quis.
      </p>
      <p class="text-justify">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Id voluptates
        iusto quo hic magnam quae?
      </p>
    </div>
    <div class="flex flex-col">
      <button class="bg-gray-200 px-9 py-3 rounded mb-3">
        <nuxt-link to="/movies">Movie List</nuxt-link>
      </button>
      <button class="border border-gray-200 px-9 py-3 rounded">
        <nuxt-link to="/movies">About Film Puff</nuxt-link>
      </button>
    </div>
  </main>
</template>

<script>
export default {}
</script>
