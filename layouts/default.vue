<template>
  <div class="h-screen w-full bg-gray-50 p-4">
    <nav
      class="flex justify-center items-center bg-gray-300 h-9 w-9 absolute right-3 cursor-pointer"
    >
      Nav
    </nav>
    <Nuxt />
    <footer
      class="absolute bottom-0 text-center w-full bg-gray-400 left-0 py-1"
    >
      Copyright &copy; {{ currentYear }} Film Puff
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear(),
    }
  },
}
</script>
