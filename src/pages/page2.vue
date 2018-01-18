<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <a href="javascript:void(0)" @click="goback">this.$router.go(-1)</a>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'This is Page 2'
    }
  },
  methods: {
    goback () {
      this.$router.go(-1)
    }
  }
}
</script>
