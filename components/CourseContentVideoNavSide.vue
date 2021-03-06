<template>
  <div ref="scrollBox" class="scroll-box" :style="`height: ${height}px;`">
    <div v-for="video in sortedVideos"
         :ref="`video-${video.id}`"
         :key="video.id"
         :class="['pa-3', 'video-row', 'white-text', video.id == selectedVideo.id ? 'active' : '', videoIsPublished(video) ? 'published' : 'upcoming']"
         @click="goToVideo(video)">
      <v-row class="pa-0 ma-0">
        <v-col cols="12" md="8" class="py-0">
          <div class="subheader video-title">{{video.name}}</div>
          <ProVideoFreePeriodCountdown :video="video" :selectedVideo="selectedVideo" />
        </v-col>
        <v-col cols="12" md="4" class="py-0">
          <div v-if="videoIsPublished(video)">
            <span class="icon-column"><ProMarker :isFree="!video.pro" :video="video" /></span>
            <span class="icon-column"><font-awesome-icon icon="check" v-if="isPlayed(video.id)" /></span>
            <DurationDisplay :duration="video.duration" />
          </div>
          <div v-else>
            <span class="caption font-italic">Available on <DateDisplay :date="video.published_at" class="small" /></span>
          </div>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<script>
  import { mapGetters } from 'vuex';
  import ProMarker from '@/components/ProMarker.vue';
  import DurationDisplay from '@/components/DurationDisplay.vue';
  import ProVideoFreePeriodCountdown from "~/components/ProVideoFreePeriodCountdown";
  import DateDisplay from "~/components/DateDisplay";
  export default {
    data(){
      return {
        currentTime: Date.now(),
        height: 100
      }
    },
    components: {
      DateDisplay,
      ProVideoFreePeriodCountdown,
      ProMarker,
      DurationDisplay
    },
    props: {
      sortedVideos: {
        type: Array,
        required: true
      },
      selectedVideo: {
        type: Object,
        required: true
      },
      clickAction: {
        type: Function,
        required: true
      },
    },
    mounted(){
      this.calculateHeight();
      window.addEventListener("resize", this.calculateHeight);
      this.scrollToCurrentVideo();
    },
    destroyed(){
      window.removeEventListener("resize", this.calculateHeight);
    },
    methods: {
      scrollToCurrentVideo() {
        const selectedVideoTopOffset = this.$refs[`video-${this.selectedVideo.id}`][0].offsetTop
        const currentScrollPosition = this.$refs.scrollBox.scrollTop
        const videoListItemHeight = 72
        if (selectedVideoTopOffset > this.height + currentScrollPosition) {
          this.$refs.scrollBox.scrollTop = selectedVideoTopOffset - (this.height / 2) + videoListItemHeight
        }
      },
      calculateHeight(){
        this.height = document.getElementById('video-player-with-sidenav').clientHeight
      },
      goToVideo(video){
        if(this.videoIsPublished(video)){
          this.$router.push(`/watch/${video.id}`)
        }
      },
      videoIsPublished(video){
        return video.published_at.getTime() < this.currentTime
      }
    },
    computed: {
      ...mapGetters({
        isPlayed: 'user/videoIsPlayed',
      }),
    }
  }
</script>

<style lang="scss" scoped>
  .pro-time-left {
    font-size: 0.8em;
  }
  .video-row:hover, .video-row.active {
    .pro-time-left {
      color: #fff !important;
    }
  }
  .scroll-box {
    overflow-y: auto;
    background-color: #111;
  }
  .icon-column {
    width: 20px;
    display: inline-block;
  }
  .white-text {
    color: #EEE;
  }
  .video-row {
    cursor: pointer;

    &.upcoming {
      cursor: auto;
    }

    &:nth-of-type(2n) {
      background-color: #222;
    }

    &.active, &:hover {
      &.published {
        color: black !important;
        background-color: #4BAF51;
      }

      &.upcoming {
        background-color: #2B5F31;
      }
    }
  }
</style>
