<template>
<div>
  <video-player class="vjs-custom-skin video-player"
                ref="videoPlayer"
                :options="playerOptions"
                customEventName="changed">
  </video-player>
</div>
</template>

<script>

export default {
  name: "TheVido",
  data () {
    return {
      playerOptions: { // video播放参数设置
        // height: '360',
        width: '200px',
        autoplay: false, // 如果true,浏览器准备好时开始回放。
        muted: true,
        preload: 'auto', // 建议浏览器在<video>加载元素后是否应该开始下载视频数据。auto浏览器选择最佳行为,立即开始加载视频（如果浏览器支持）
        language: 'en',
        aspectRatio: '16:9', // 将播放器置于流畅模式，并在计算播放器的动态大小时使用该值。值应该代表一个比例 - 用冒号分隔的两个数字（例如"16:9"或"4:3"）
        fluid: true, // 当true时，Video.js player将拥有流体大小。换句话说，它将按比例缩放以适应其容器。
        playbackRates: [0.7, 1.0, 1.5, 2.0], // 播放速度
        notSupportedMessage: '此视频暂无法播放，请稍后再试', // 允许覆盖Video.js无法播放媒体源时显示的默认信息。
        sources: [{
          type: "video/mp4",
          // mp4
          src: "http://vjs.zencdn.net/v/oceans.mp4"
          // webm
          // src: "https://cdn.theguardian.tv/webM/2015/07/20/150716YesMen_synd_768k_vp8.webm"
        }],
        // controlBar: {
        //   timeDivider: true,
        //   durationDisplay: true,
        //   remainingTimeDisplay: false,
        //   fullscreenToggle: true // 全屏按钮
        // },
        poster: "https://surmon-china.github.io/vue-quill-editor/static/images/surmon-1.jpg" // 封面地址
      }
    }
  }
}
</script>

<style scoped>

</style>
