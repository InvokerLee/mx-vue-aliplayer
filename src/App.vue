<template>
  <div id="app">
    <!-- example -->
    <mx-vue-aliplayer ref="player" :source="source" @ready="ready" @error="error"></mx-vue-aliplayer>
    <button @click="play">播放</button>
    <button @click="pause">暂停</button>
    <button @click="replay">重播</button>
  </div>
</template>

<script>
import MxVueAliplayer from './packages/mx-vue-aliplayer'

export default {
  name: 'App',
  components: {
    MxVueAliplayer
  },
  data() {
    return {
      source: '//player.alicdn.com/video/aliyunmedia.mp4',
    }
  },
  methods: {
    error (e) {
      console.log(e)
    },
    ready () {
      console.log('播放器ready了')
    },
    play() {
      const player = this.$refs.player;
      player && player.play();
    },
    pause() {
      const player = this.$refs.player;
      player && player.pause();
    },
    replay() {
      const player = this.$refs.player;
      player && player.replay();
    },
  },
}
</script>
