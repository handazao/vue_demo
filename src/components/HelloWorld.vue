<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div id="player"></div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted: function () {
    /* eslint-disable */
    // 添加DOM容器
    const player = new ImouPlayer('#player');
    // 播放器初始化
    player.setup({
      src: [
        {
          url: 'imou://open.lechange.com/5L04995RAJF6580/0/1?streamId=1', // url拼接说明请见：2.2.3 轻应用播放地址说明
          kitToken: 'Kt_56e8f24521e3404e87114a590d2720f1', // 播放Token，通过接口getKitToken获取，具体请见：2.2.4 getKitToken接口协议说明
        }
      ], // 播放地址
      width: 760, // 播放器宽度
      height: 400, // 播放器高度
      poster: '', // 封面图url
      autoplay: false,
      controls: true, // 是否展示控制栏
    });

    // 播放
    player.play();
    // 暂停
    player.pause();
    // 停止播放
    player.stop();
    // 销毁播放器
    player.destroy();
    // 进入全屏
    player.setFullScreen();
    // 退出全屏
    player.exitFullScreen();
    // 设置音量
    player.setVolume(0.5);
    // 设置多屏
    player.setMultiScreen(4);
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
