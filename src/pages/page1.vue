<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <a href="javascript:void(0)" @click="goback">this.$router.go(-1)</a>
    <br>
    <router-link :to="'page2'">go to page2 </router-link>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'This is Page 1'
    }
  },
  methods: {
    goback () {
      this.$router.go(-1)
    }
  }
}
</script>
