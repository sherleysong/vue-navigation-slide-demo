<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <router-link to="page1">go to page1</router-link>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'This is Page Home'
    }
  }
}
</script>
