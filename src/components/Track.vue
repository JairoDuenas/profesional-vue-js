<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="card">
    <div class="card-image">
      <figure class="image is-1by1">
        <img :src="track.album.images[0].url" alt="image" />
      </figure>
    </div>
    <div class="card-content">
      <div class="media">
        <div class="media-left">
          <figure class="image is-48x48">
            <img :src="track.album.images[0].url" alt="image" />
          </figure>
        </div>
        <div class="media-content">
          <p class="title is-6">
            <strong>{{ track.name }}</strong>
          </p>
          <p class="subtitle is-6">{{ track.artists[0].name }}</p>
        </div>
      </div>
      <div class="content">
        <small>{{ track.duration_ms }}</small>
        <nav class="level is-mobile">
          <div class="level-left">
            <a class="level-item">
              <div class="icon is-small" @click="selectTrack">▶️</div>
            </a>
          </div>
        </nav>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    track: {
      type: Object,
      required: true
    }
  },
  methods: {
    selectTrack () {
      this.$emit('select', this.track.id)
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
