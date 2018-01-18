<template>
  <div id="app">
    <!-- <transition :name="transitionName"> -->
    <transition :name="transitionName">
      <navigation>
        <router-view/>
      </navigation>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      transitionName: 'fade'
    }
  },
  created () {
    // bind event
    this.$navigation.on('forward', (to, from) => {
      console.log('forward to', to, 'from ', from)
      this.transitionName = 'slide-left'
    })
    this.$navigation.on('back', (to, from) => {
      console.log('back to', to, 'from ', from)
      this.transitionName = 'slide-right'
    })
    this.$navigation.on('replace', (to, from) => {
      console.log('replace to', to, 'from ', from)
    })
    this.$navigation.on('refresh', (to, from) => {
      console.log('refresh to', to, 'from ', from)
    })
    this.$navigation.on('reset', () => {
      console.log('reset')
    })
    // and use [once, off] methods
    this.$navigation.once('forward', () => {
      console.log('appear once')
    })
    const off = () => {
      console.log('will not appear')
    }
    this.$navigation.on('forward', off)
    this.$navigation.off('forward', off)
  }

}
</script>

<style>
a {
  color: red;
  text-decoration: underline;
}

.hello {
  position: absolute;
  transition: all .3s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.slide-left-enter,
.slide-right-leave-to {
  opacity: 0;
  transform: translate(100%, 0);
}
.slide-right-enter,
.slide-left-leave-to {
  opacity: 0;
  transform: translate(-100%, 0);
}
</style>
