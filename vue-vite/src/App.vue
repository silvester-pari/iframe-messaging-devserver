<template>
  <div>
    Vite App Messages:
    <ul>
      <li
        v-for="(message, index) in messages"
        :key="index"
      >
        {{ message }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: () => ({
    messages: []
  }),
  created() {
    window.addEventListener('message', (event) => {
      this.messages.push(event.data)
    })
  }
}
</script>