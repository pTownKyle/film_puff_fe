<template>
  <div class="h-screen w-full bg-gray-50 p-4">
    <header>
      <button
        class="flex justify-center items-center bg-gray-300 h-9 w-9 absolute right-3 cursor-pointer z-10"
        @click="showNav"
      >
        Nav
      </button>
      <nav
        class="bg-gray-500 h-full z-0 w-1/2 absolute top-0 right-0"
        v-if="navOpen"
      >
        <div class="h-3/4 flex flex-col justify-center">
          <ul class="flex flex-col space-y-6 h-1/2">
            <li
              class="border-b border-t py-3 border-white text-center"
              v-for="link in navLinks"
              :key="link.name"
              @click="showNav"
            >
              <nuxt-link :to="link.link">{{ link.name }}</nuxt-link>
            </li>
          </ul>
        </div>
      </nav>
    </header>
    <div class="h-full w-full" @click="closeNav">
      <Nuxt />
    </div>
    <footer
      class="absolute bottom-0 text-center w-full bg-gray-400 left-0 py-1"
    >
      &copy; {{ currentYear }} <nuxt-link to="/">Film Puff</nuxt-link>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear(),
      navOpen: false,
      navLinks: [
        { name: 'Home', link: '/' },
        { name: 'Movies', link: '/movies' },
        { name: 'About', link: '/about' },
        { name: 'Contact', link: '/contact' },
      ],
    }
  },
  methods: {
    showNav() {
      this.navOpen = !this.navOpen
    },
    closeNav() {
      if (this.navOpen) {
        this.navOpen = false
      }
    },
  },
}
</script>
