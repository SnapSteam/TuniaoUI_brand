<template>
  <view class="template-home tn-safe-area-inset-bottom">

    <!-- 顶部自定义导航 -->
    <tn-nav-bar :isBack="false" :bottomShadow="false" backgroundColor="#FFFFFF00">
      <view class="custom-nav tn-flex tn-flex-col-center tn-flex-row-left">
        <view class="custom-nav__logo" @click="tn('')">
          <view class="tn-icon-menu-grille tn-color-white"></view>
        </view>
        <view class="tn-flex-col-center tn-flex-row-center tn-text-lg" style="margin-left: 25vw;">
          <text class="tn-text-xxl tn-color-white">TN Fashion</text>
        </view>
      </view>
    </tn-nav-bar>

    <!-- 黑色滚动背景 -->
    <view class="bg-contaniner" style="background-color: #000000;">
    </view>

    <!-- 套娃式轮播 -->
    <view class="">
      <swiper class="card-swiper" :circular="false" vertical="true" :autoplay="false" duration="500" interval="5000"
        @change="cardSwiper">


        <!-- 纵向滚动的轮播-视频形式 -->
        <swiper-item v-for="(item,index) in swiperList" :key="index" :class="cardCur==index?'cur':''">
          <!-- 视频 -->
          <view class="swiper-item image-banner">
            <video :id="`video-${item.id}`" :src="item.mp4" object-fit="cover" muted :mobilenet-hint-type="0"
              :enable-progress-gesture="false" :show-loading='false' :show-play-btn='false' :show-fullscreen-btn='false'
              :controls='false' :autoplay='true' :enable-play-gesture='true' :loop="true"
              style="height: 100vh;width: 100vw;"></video>
          </view>
          <!-- 文字 -->
          <view class="swiper-item-icon image-banner">
            <view class="swiper-item-text">
              <view class="tn-color-white tn-text-xxl tn-text-bold tn-text-center">
                <text class="tn-padding-right-xs" :class="['tn-icon-' + item.icon]"></text>
                <text class="">{{item.user}}</text>
              </view>
              <view class="tn-color-white tn-padding-top-xs tn-text-df clamp-text-2 tn-text-center tn-margin-top-sm"
                style="opacity: 0.8;">
                {{item.title}}
              </view>
            </view>
            <!-- 按钮 -->
            <view class="tn-flex go">
              <view class="tn-flex-1 justify-content-item tn-margin-sm tn-text-center">
                <tn-button :plain="true" shape="round" backgroundColor="#FFFFFF" fontColor="#FFFFFF" width="40vw"
                  height="70rpx" @click="tn('/productPages/details')">
                  即刻探索
                  <text class="tn-icon-right-arrow tn-padding-left-xs"></text>
                </tn-button>
              </view>
            </view>
          </view>
        </swiper-item>

        <!-- 纵向滚动的轮播 -->
        <swiper-item>
          <view class="" style="height: 100vh;width: 100vw;">
            <!-- 横向滚动的轮播-套娃 -->
            <swiper class="img-swiper tn-margin-top-lg" :circular="true" :autoplay="false" duration="500"
              interval="5000" previous-margin="60rpx" next-margin="60rpx" @change="imgSwiper">
              <swiper-item v-for="(item,index) in swiperList2" :key="index" :class="imgCur==index?'cur':''">
                <view class="swiper-item img-banner" :style="'background-image:url('+ item.url + ');'">
                </view>
                <view class="swiper-item-text1 tn-color-white">
                  <view class="tn-flex tn-flex-row-between">
                    <view class="tn-text-xl">
                      {{item.name}}
                    </view>
                    <view class="tn-text-right">
                      <view class="">
                        {{item.number}}
                      </view>
                    </view>
                  </view>
                </view>
                <view class="swiper-item-text2">
                  <view class="tn-text-sm tn-padding-top-xs tn-text-center tn-color-white clamp-text-1">{{item.text}}
                  </view>
                </view>
                <view class="tn-flex  go2">
                  <view class="tn-flex-1 justify-content-item tn-margin-sm tn-text-center">
                    <tn-button :plain="true" shape="round" backgroundColor="#FFFFFF" fontColor="#FFFFFF" width="40vw"
                      height="70rpx" @click="tn('/productPages/details')">
                      即刻探索
                      <text class="tn-icon-right-arrow tn-padding-left-xs"></text>
                    </tn-button>
                  </view>
                </view>
              </swiper-item>
            </swiper>
          </view>
        </swiper-item>

      </swiper>
      

      <!-- 轮播提示小点点鸭-->
      <view class="indication" v-if="cardCur==3" style="display: none;">
        <block v-for="(item,index) in swiperList" :key="index">
          <view class="spot" :class="cardCur==index?'active':''"></view>
        </block>
      </view>
      <view class="indication" v-else>
        <block v-for="(item,index) in 4" :key="index">
          <view class="spot" :class="cardCur==index?'active':''"></view>
        </block>
      </view>


    </view>


  </view>
</template>

<script>
  export default {
    name: 'Home',
    data() {
      return {
        cardCur: 0,
        swiperList: [{
          id: 0,
          type: 'image',
          url: 'https://cdn.nlark.com/yuque/0/2022/jpeg/280373/1664005699066-assets/web-upload/f7a37b29-506a-4e79-937f-826334902bb4.jpeg',
          mp4: 'https://resource.tuniaokj.com/images/new/tn_003.mp4',
          icon: 'con-pisces',
          user: '尊享专属服务',
          title: '图鸟国际 · 时尚生活',
        }, {
          id: 1,
          type: 'image',
          url: 'https://resource.tuniaokj.com/images/blogger/blogger_beibei.jpg',
          mp4: 'https://resource.tuniaokj.com/images/new/tn_002.mp4',
          icon: 'con-cancer',
          user: '尊享专属折扣',
          title: '图鸟国际 · 简约生活',
        }, {
          id: 2,
          type: 'image',
          url: 'https://cdn.nlark.com/yuque/0/2022/jpeg/280373/1664179989916-assets/web-upload/eda197eb-42ce-44b1-9b14-fce3481db603.jpeg',
          mp4: 'https://resource.tuniaokj.com/images/new/tn_005.mp4',
          icon: 'con-leo',
          user: '尊享专属客服',
          title: '图鸟国际 · 悠享生活',
        }],


        imgCur: 0,
        swiperList2: [{
          id: 0,
          type: 'image',
          number: "一",
          name: "橙色卫衣和榨芒果汁",
          text: "晚风轻踩着云朵，月亮在贩售快乐",
          url: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683906320444-assets/web-upload/efc56953-c719-46ec-ad24-1f207516ca9d.jpeg',
        }, {
          id: 1,
          type: 'image',
          number: "二",
          name: "淡红外套和白色衬衫",
          text: "我不喜欢带伞，因为雨水从不滴落在我的心上",
          url: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683905799657-assets/web-upload/7e3e822c-e054-4319-9b1f-5db58be0023e.jpeg',
        }, {
          id: 2,
          type: 'image',
          number: "三",
          name: "条纹V衫和单肩背包",
          text: "图鸟在这里，和你一起共同成长",
          url: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683907347231-assets/web-upload/0f7ae432-0a19-44fb-ba99-47fe41537f11.jpeg',
        }, {
          id: 3,
          type: 'image',
          number: "四",
          name: "黑色皮套和黑色书包",
          text: "你从银河背后靠近我，我与星辉一同为你沉沦",
          url: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683906918806-assets/web-upload/a9f24fd8-3fde-4e96-a0c5-773cb10829b1.jpeg',
        }, {
          id: 4,
          type: 'image',
          number: "五",
          name: "全身风衣和蓝色衬衫",
          text: "生活需要一些仪式感，这跟矫情无关",
          url: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683905940454-assets/web-upload/4a4d5700-d88a-47ab-ab5e-fbbb50609528.jpeg',
        }, {
          id: 5,
          type: 'image',
          number: "六",
          name: "牛仔外套和粉色帽子",
          text: "感谢你，带给我一年四季的陪伴与支持",
          url: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683906549731-assets/web-upload/112734a9-fec7-427f-901a-bed1a34dacd0.jpeg',
        }],


      }
    },
    onLoad() {},
    methods: {
      // cardSwiper
      cardSwiper(e) {
        this.cardCur = e.detail.current
      },
      // imgSwiper
      imgSwiper(e) {
        this.imgCur = e.detail.current
      },
      // 短震动跳转
      tn(e) {
        wx.vibrateShort();
        uni.navigateTo({
          url: e,
        });
      },
    }
  }
</script>

<style lang="scss" scoped>
  .template-home {
    max-height: 100vh;
  }

  /* 底部安全边距 start*/
  .tn-tabbar-height {
    min-height: 120rpx;
    height: calc(140rpx + env(safe-area-inset-bottom) / 2);
    height: calc(140rpx + constant(safe-area-inset-bottom));
  }

  /* 自定义导航栏内容 start */
  .custom-nav {
    height: 100%;

    &__logo {
      margin: auto 5rpx;
      font-size: 50rpx;
      margin-right: 10rpx;
      margin-left: 30rpx;
      flex-basis: 5%;
    }
  }
  /* 自定义导航栏内容 end */
  
  // css不写多一些，页面的玩法就很难炫起来，所以别吐槽css多了，下方分类的很清晰了的，且尽量不用那种看不懂的css写法了的

  /* 全屏轮播  start*/
  .card-swiper {
    height: 100vh !important;
    margin-top: -4rpx;
  }

  .card-swiper swiper-item {
    width: 750rpx !important;
    left: 0rpx;
    box-sizing: border-box;
    overflow: initial;
  }

  .card-swiper swiper-item .swiper-item {
    width: 100%;
    display: block;
    height: 100vh;
    border-radius: 0rpx;
    transform: scale(1);
    transition: all 0.2s ease-in 0s;
    will-change: transform;
    overflow: hidden;
  }

  .card-swiper swiper-item.cur .swiper-item {
    transform: none;
    transition: all 0.2s ease-in 0s;
    will-change: transform;
  }

  .card-swiper swiper-item .swiper-item-text {
    margin-top: -680rpx;
    // margin-top: calc(-380rpx + env(safe-area-inset-bottom) / 2);
    // margin-top: calc(-380rpx + constant(safe-area-inset-bottom));
    background: none;
    width: 100%;
    display: block;
    height: 50vh;
    // border-radius: 10rpx;
    transform: translate(0rpx, 0rpx) scale(1);
    transition: all 0.6s ease 0s;
    will-change: transform;
    overflow: hidden;
  }

  .card-swiper swiper-item.cur .swiper-item-text {
    background: linear-gradient(0deg, rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0));
    margin-top: -680rpx;
    // margin-top: calc(-380rpx - env(safe-area-inset-bottom) / 2);
    // margin-top: calc(-380rpx - constant(safe-area-inset-bottom));
    width: 100%;
    height: 50vh;
    padding: 30rpx 10rpx 180rpx 30rpx;
    transform: translate(0rpx, 0rpx) scale(1);
    transition: all 0.6s ease 0s;
    will-change: transform;
  }


  /* 即刻探索 start*/
  .card-swiper swiper-item .go {
    z-index: 9999;
    width: 100%;
    position: fixed;
    margin: 0 auto;
    bottom: 190rpx;
    bottom: calc(210rpx + env(safe-area-inset-bottom) / 2);
    bottom: calc(210rpx + constant(safe-area-inset-bottom));
  }

  .card-swiper swiper-item.cur .go {
    z-index: 9999;
    width: 100%;
    position: fixed;
    margin: 0 auto;
    bottom: 190rpx;
    bottom: calc(210rpx + env(safe-area-inset-bottom) / 2);
    bottom: calc(210rpx + constant(safe-area-inset-bottom));
  }

  .card-swiper swiper-item .swiper-item-icon {
    // transform: translate(0rpx, 0rpx) scale(1, 1);
    transition: all 0.6s ease 0s;
    // overflow: hidden;
  }

  .card-swiper swiper-item.cur .swiper-item-icon {
    // transform: translate(0rpx, 0rpx) scale(1, 1);
    transition: all 0.6s ease 0s;
  }


  /* 轮播图片入口 start*/
  .img-swiper {
    height: 86vh !important;
  }

  .img-swiper swiper-item {
    width: 630rpx !important;
    box-sizing: border-box;
    padding: 0rpx 0rpx 90rpx 0rpx;
    overflow: initial;
  }

  .img-swiper swiper-item .swiper-item {
    width: 100%;
    display: block;
    height: 860rpx;
    transform: scale(0.9);
    transition: all 0.2s ease-in 0s;
    overflow: hidden;
  }

  .img-swiper swiper-item.cur .swiper-item {
    transform: none;
    transition: all 0.2s ease-in 0s;
  }

  /* 即刻探索 start*/
  .img-swiper swiper-item .go2 {
    z-index: 9999;
    width: 100%;
    position: fixed;
    margin: 0 auto;
    bottom: 0rpx;
    bottom: calc(20rpx + env(safe-area-inset-bottom) / 2);
    bottom: calc(20rpx + constant(safe-area-inset-bottom));
  }

  .img-swiper swiper-item.cur .go2 {
    z-index: 9999;
    width: 100%;
    position: fixed;
    margin: 0 auto;
    bottom: 0rpx;
    bottom: calc(20rpx + env(safe-area-inset-bottom) / 2);
    bottom: calc(20rpx + constant(safe-area-inset-bottom));
  }

  .img-swiper swiper-item .swiper-item-text1 {
    margin-top: -980rpx;
    width: 80%;
    display: block;
    height: 50%;
    transform: translate(60rpx, 0rpx) scale(1);
    opacity: 0.4;
    transition: all 0.6s ease 0s;
    overflow: hidden;
  }

  .img-swiper swiper-item.cur .swiper-item-text1 {
    margin-top: -980rpx;
    margin-right: 150rpx;
    width: 100%;
    opacity: 1;
    transform: translate(0rpx, 0rpx) scale(1);
    transition: all 0.6s ease 0s;
  }

  .img-swiper swiper-item .swiper-item-text2 {
    background: linear-gradient(0deg, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0));
    margin-top: 220rpx;
    /* width: 83%; */
    // width: 100%;
    display: block;
    height: 140rpx;
    padding: 20rpx 30rpx 0 30rpx;
    transform: translate(0rpx, 0rpx) scale(1);
    opacity: 0;
    transition: all 0.6s ease 0s;
    overflow: hidden;
  }

  .img-swiper swiper-item.cur .swiper-item-text2 {
    // width: 100%;
    height: 140rpx;
    margin-top: 220rpx;
    padding: 20rpx 30rpx 0 30rpx;
    opacity: 1;
    transform: translate(0rpx, 0rpx) scale(1);
    transition: all 0.6s ease 0s;
  }

  .img-banner {
    margin-top: 320rpx;
    display: flex;
    background-size: cover;
    background-repeat: no-repeat;
    // background-attachment:fixed;
    background-position: center;
    align-items: center;
    justify-content: center;
  }

  /* 轮播图片 start*/
  .pic-swiper {
    height: 67vh !important;
  }

  .pic-swiper swiper-item {
    width: 630rpx !important;
    // left: 60rpx;
    box-sizing: border-box;
    padding: 0rpx 0rpx 90rpx 0rpx;
    overflow: initial;
  }

  .pic-swiper swiper-item .pic-item {
    width: 100%;
    display: block;
    height: 100%;
    border-radius: 10rpx;
    transform: scale(0.9);
    transition: all 0.2s ease-in 0s;
    overflow: hidden;
  }

  .pic-swiper swiper-item.cur .pic-item {
    transform: none;
    transition: all 0.2s ease-in 0s;
  }

  .pic-swiper swiper-item .pic-item-text {
    margin-top: -180rpx;
    width: 100%;
    display: block;
    height: 50%;
    border-radius: 10rpx;
    transform: translate(0rpx, -40rpx) scale(0.7, 0.7);
    transition: all 0.6s ease 0s;
    overflow: hidden;
  }

  .pic-swiper swiper-item.cur .pic-item-text {
    margin-top: -150rpx;
    width: 100%;
    transform: translate(0rpx, 0rpx) scale(0.9, 0.9);
    transition: all 0.6s ease 0s;
  }

  
  /* 轮播指示点 start*/
  .indication {
    z-index: 9999;
    width: 100%;
    height: 36rpx;
    position: fixed;
    // display:flex;
    display: block;
    flex-direction: row;
    align-items: center;
    justify-content: center;
  }
  
  .spot {
    opacity: 0.6;
    background-color: #FFF;
    opacity: 0.3;
    width: 10rpx;
    height: 10rpx;
    border-radius: 20rpx;
    margin: 20rpx 0 !important;
    left: 90vw;
    top: -340rpx;
    position: relative;
  }
  
  .spot.active {
    opacity: 0.4;
    height: 30rpx;
    background-color: #FFF;
  }
  
  /* 文字截取*/
  .clamp-text-1 {
    -webkit-line-clamp: 1;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    text-overflow: ellipsis;
    overflow: hidden;
  }
  
  .clamp-text-2 {
    -webkit-line-clamp: 2;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    text-overflow: ellipsis;
    overflow: hidden;
  }
  

  /* 移动背景部分 start*/
  .bg-contaniner {
    position: fixed;
    top: -0rpx;
    left: -300rpx;
    --text-color: hsl(0 95% 60%);
    --bg-color: hsl(0 0% 100%);
    --bg-size: 200px;
    height: 100%;
    display: grid;
    place-items: center;
    place-content: center;
    overflow: hidden;
    background-color: var(--bg-color);
    z-index: -1;
  }

  .bg-contaniner::before {
    --size: 150vmax;
    content: "";
    inline-size: var(--size);
    block-size: var(--size);
    background-image: url("https://cdn.nlark.com/yuque/0/2023/png/280373/1685589478750-assets/web-upload/1266f58d-48a7-4799-b3d8-02640f5712d3.png");
    background-size: var(--bg-size);
    background-repeat: repeat;
    transform: rotate(45deg);
    opacity: 0.25;
    animation: bg 6s linear infinite;
  }

  @media (prefers-reduced-motion: reduce) {
    .bg-contaniner::before {
      animation-duration: 0s;
    }
  }

  @keyframes bg {
    to {
      background-position: 0 calc(var(--bg-size) * -1);
    }
  }
  /* 移动背景部分 end*/
  
</style>
