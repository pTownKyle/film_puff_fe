<template>
  <main class="h-full flex flex-col items-center justify-center">
    <h1 class="text-3xl">Send Us A Smoke Signal</h1>
    <div class="p-3">
      <form @submit.prevent="sendEmail" class="w-full flex flex-col">
        <label for="sendersName">Name</label>
        <input
          type="text"
          name="sendersName"
          id="sendersName"
          placeholder="Your Name..."
          class="mb-3"
          v-model="sendersName"
        />
        <label for="sendersEmail">Email</label>
        <input
          type="email"
          name="sendersEmail"
          id="sendersEmail"
          placeholder="Your Email..."
          class="mb-3"
          v-model="sendersEmail"
        />
        <label for="sendersMessage">Message</label>
        <textarea
          name="sendersMessage"
          id="sendersMessage"
          placeholder="Your Message..."
          class="mb-6"
          v-model="sendersMessage"
        ></textarea>
        <button type="submit">Send</button>
      </form>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      sendersName: '',
      sendersEmail: '',
      sendersMessage: '',
    }
  },
  methods: {
    sendEmail() {
      console.log(`
        Sender's Name: ${this.sendersName}
        Sender's Email: ${this.sendersEmail}
        Sender's Message: ${this.sendersMessage}
      `)

      this.sendersName = ''
      this.sendersEmail = ''
      this.sendersMessage = ''
    },
  },
}
</script>
