<template>
  <section class="container">
    <h1>{{ title }}</h1>
    <p v-html="message">no message.</p>
    <hr />
    <div class="right">
      <router-link to="/">Go to Top</router-link>
    </div>
  </section>
</template>

<script>
export default {
  validate({ params }) {
    return !(params.id === undefined || params.pass === undefined)
  },
  data() {
    return {
      title: 'Login',
    }
  },
  computed: {
    message() {
      const id = this.$route.params.id
      const pass = this.$route.params.pass
      return 'ID: ' + id + '<br>PASS: ' + pass
    },
  },
}
</script>

<style>
.container {
  padding: 5px 10px;
}

h1 {
  font-size: 60pt;
  color: #345980;
}

p {
  padding-top: 5px;
  font-size: 20px;
}

a {
  font-size: 16pt;
}

.right {
  text-align: right;
}
</style>
