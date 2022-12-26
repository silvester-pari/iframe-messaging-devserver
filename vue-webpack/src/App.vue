<template>
  <div>
    <p>Webpack App Messages:</p>
    <li
      v-for="(message, index) in messages"
      :key="index"
    >
      {{ message }}
    </li>
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