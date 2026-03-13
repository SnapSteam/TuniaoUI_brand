<template>
  <view class="template-details tn-safe-area-inset-bottom">
    <!-- 顶部自定义导航 -->
    <tn-nav-bar fixed alpha customBack>
      <view slot="back" class='tn-custom-nav-bar__back'
        @click="goBack">
        <text class='icon tn-icon-left'></text>
        <text class='icon tn-icon-home-capsule-fill'></text>
      </view>
    </tn-nav-bar>
    
    <swiper class="card-swiper" :circular="true"
      :autoplay="true" duration="500" interval="16000" @change="cardSwiper"> 
      <swiper-item v-for="(item,index) in swiperList" :key="index" :class="cardCur==index?'cur':''">
        <view class="swiper-item image-banner">
          <image :src="item.url" mode="aspectFill" v-if="item.type=='image'"></image>
        </view>
      </swiper-item>
    </swiper>
    <view class="indication">
        <block v-for="(item,index) in swiperList" :key="index">
            <view class="spot" :class="cardCur==index?'active':''"></view>
        </block>
    </view>
    
    <view class="tn-margin">
      <view class="tn-flex tn-flex-row-between">
        <view class="justify-content-item tn-text-bold tn-margin-top-xs" style="font-size: 38rpx;">
          全身风衣和蓝色衬衫
        </view>
        <view class="justify-content-item tn-margin-top-sm">
          <view class="tn-flex tn-flex-row-center tn-flex-col-center" @click="tn('')">
            <button class="tn-button--clear-style" open-type="share">
              <view class="tn-icon-upload-simple tn-color-gray tn-text-xl"></view>
            </button>
          </view>
        </view>
      </view>
      <view class="tn-flex tn-flex-row-between tn-margin-top">
        <view class="justify-content-item" style="font-size: 50rpx;color: #3e4864;margin-left: -8rpx;">
          <text class="">￥</text>
          <text class="">298.00</text>
        </view>
        <view class="justify-content-item tn-color-gray tn-padding-top-sm">
          <view class="">已售 16</view>
        </view>
      </view>
    </view>
    
    <!-- 边距间隔 -->
    <view class="tn-strip-bottom"></view>
    
    
    <!-- 更多信息-->
    <view class="tn-padding-top-sm tn-padding-bottom-sm">
      <tn-list-cell :hover="true" :unlined="true" :radius="true" :fontSize="30">
        <view class="tn-flex tn-flex-col-center">
          <view class="tn-flex-1">尺寸</view>
          <view class="tn-margin-left-sm">
            <view class="tn-flex tn-flex-row-between tn-bg-white">
              <view class="tn-padding-xs tn-radius">
                <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
                  <view class="icon12__item--icon tn-flex tn-flex-row-center tn-flex-col-center">
                    <view class="tn-color-gray">XS</view>
                  </view>
                </view>
              </view>
              <view class="tn-padding-xs tn-radius">
                <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
                  <view class="icon12__item--icon tn-flex tn-flex-row-center tn-flex-col-center">
                    <view class="tn-color-gray">S</view>
                  </view>
                </view>
              </view>
              <view class="tn-padding-xs tn-radius">
                <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
                  <view class="icon12__item--icon tn-flex tn-flex-row-center tn-flex-col-center tn-bg-black">
                    <view class="tn-color-white">M</view>
                  </view>
                </view>
              </view>
              <view class="tn-padding-xs tn-radius">
                <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
                  <view class="icon12__item--icon tn-flex tn-flex-row-center tn-flex-col-center">
                    <view class="tn-color-gray">L</view>
                  </view>
                </view>
              </view>
              <view class="tn-padding-xs tn-radius">
                <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
                  <view class="icon12__item--icon tn-flex tn-flex-row-center tn-flex-col-center">
                    <view class="tn-color-gray">XL</view>
                  </view>
                </view>
              </view>
            </view>
          </view>
        </view>
      </tn-list-cell>
      <tn-list-cell :hover="true" :unlined="true" :radius="true" :fontSize="30">
        <view class="tn-flex tn-flex-col-center">
          <view class="tn-flex-1">颜色</view>
          <view class="">
            <view class="tn-flex tn-flex-row-between tn-bg-white">
              <view class="tn-padding-xs tn-radius">
                <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
                  <view class="icon15__item--icon tn-flex tn-flex-row-center tn-flex-col-center" style="border: 2rpx solid #E6E6E6;">
                    <view class="" style="width: 30rpx;height: 30rpx;border-radius: 100rpx;background-color: #3E3E70;"></view>
                  </view>
                </view>
              </view>
              <view class="tn-padding-xs tn-radius">
                <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
                  <view class="icon15__item--icon tn-flex tn-flex-row-center tn-flex-col-center" style="border: 2rpx solid #E6E6E6;">
                    <view class="" style="width: 30rpx;height: 30rpx;border-radius: 100rpx;background-color: #88898D;"></view>
                  </view>
                </view>
              </view>
              <view class="tn-padding-xs tn-radius">
                <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
                  <view class="icon15__item--icon tn-flex tn-flex-row-center tn-flex-col-center" style="border: 2rpx solid #F18449;">
                    <view class="" style="width: 30rpx;height: 30rpx;border-radius: 100rpx;background-color: #F18449;"></view>
                  </view>
                </view>
              </view>
              <view class="tn-padding-xs tn-radius">
                <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
                  <view class="icon15__item--icon tn-flex tn-flex-row-center tn-flex-col-center" style="border: 2rpx solid #E6E6E6;">
                    <view class="" style="width: 30rpx;height: 30rpx;border-radius: 100rpx;background-color: #4A6AF1;"></view>
                  </view>
                </view>
              </view>
              <view class="tn-padding-xs tn-radius">
                <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
                  <view class="icon15__item--icon tn-flex tn-flex-row-center tn-flex-col-center" style="border: 2rpx solid #E6E6E6;">
                    <view class="" style="width: 30rpx;height: 30rpx;border-radius: 100rpx;background-color: #36353B;"></view>
                  </view>
                </view>
              </view>
              <view class="tn-padding-xs tn-radius">
                <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
                  <view class="icon15__item--icon tn-flex tn-flex-row-center tn-flex-col-center" style="border: 2rpx solid #E6E6E6;">
                    <view class="" style="width: 30rpx;height: 30rpx;border-radius: 100rpx;background-color: #DDDDDD;"></view>
                  </view>
                </view>
              </view>
            </view>
          </view>
        </view>
      </tn-list-cell>

    </view>
    
    
    <!-- 边距间隔 -->
    <view class="tn-strip-bottom"></view>

    <view class="content-backgroup tn-margin">
      <image src='https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1685590698924-assets/web-upload/df4f2862-26bd-4792-95ea-21bccdb1bed3.jpeg' mode='widthFix' class='backgroud-image'></image>
    </view>
    
    
    <view id="top-info" class="details-footerfixed tn-safe-area-inset-bottom tn-bg-white" :style="{transform: `translateY(${topInfoTranslateY}px)`}">
      <view class="tn-flex tn-flex-row-between tn-flex-col-center">
        <view class="tn-flex-2 justify-content-item tn-color-gray">
          <view class="tn-flex tn-flex-row-center">
            <view class="tn-flex-1" @click="goBack">
              <view class="tn-icon-home-in" style="font-size: 42rpx;"></view>
              <view class="tn-text-center tn-text-sm tn-padding-top-xs">首页</view>
            </view>
            <view class="tn-flex-1 tn-padding-right-xl">
              <button class="tn-button--clear-style" open-type="contact" style="border-radius: 0;">
                <view class="tn-icon-service-simple" style="font-size: 42rpx;"></view>
                <view class="tn-text-center tn-text-sm tn-padding-top-xs">客服</view>
              </button>
            </view>
          </view>
        </view>
        <view class="tn-flex-3 justify-content-item tn-padding-top-sm tn-padding-bottom-sm">
          <tn-button shape="round" backgroundColor="tn-bg-black" padding="38rpx 0" width="90%" :fontSize="30">
            <text class="tn-color-white" hover-class="tn-hover" :hover-stay-time="150">
              加入购物车
            </text>
          </tn-button>
        </view>
      </view>
    </view>
    

    
    <view class='tn-tabbar-height'></view>
    
  </view>
</template>

<script>
  import template_page_mixin from '@/libs/mixin/template_page_mixin.js'
  export default {
    name: 'TemplateDetails',
    mixins: [template_page_mixin],
    data(){
      return {
        cardCur: 0,
        swiperList: [{
          id: 0,
          type: 'image',
          title: '免费开源',
          name: '商业合作请联系作者',
          url: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683905940454-assets/web-upload/4a4d5700-d88a-47ab-ab5e-fbbb50609528.jpeg',
        }, {
          id: 1,
          type: 'image',
          title: '图鸟南南',
          name: '欢迎加入东东们',
          url: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683907347171-assets/web-upload/2b63ef6c-b137-4ad7-9fcb-ab427ba491a4.jpeg',
        }, {
          id: 2,
          type: 'image',
          title: '图鸟西西',
          name: '一起玩转scss',
          url: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683905799657-assets/web-upload/7e3e822c-e054-4319-9b1f-5db58be0023e.jpeg',
        }, {
          id: 3,
          type: 'image',
          title: '图鸟北北',
          name: '微信号 tnkewo',
          url: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683906918806-assets/web-upload/a9f24fd8-3fde-4e96-a0c5-773cb10829b1.jpeg',
        }],
        countOptions: [{
          icon: 'star',
          text: '收藏'
        },{
          icon: 'share-circle',
          text: '分享',
        }],
        customButtonGroups: [{
          text: '咨询客服',
          backgroundColor: 'tn-cool-bg-color-5',
          color: '#FFFFFF'
        },{
          text: '立即购买',
          backgroundColor: 'tn-cool-bg-color-15--reverse',
          color: '#FFFFFF'
        }],
        
        topInfo: {
          height: 0,
        },
        topInfoTranslateY: 0,
        prevScrollTop: 0
      }
    },
    onReady() {
      this.getTopInfoRect()
    },
    onPageScroll(e) {
      this.handlePageScroll(e.scrollTop)
    },
    methods: {
      // cardSwiper
      cardSwiper(e) {
        this.cardCur = e.detail.current
      },
      // 跳转
      tn(e) {
      	uni.navigateTo({
      		url: e,
      	});
      },


      // 获取顶部销售信息容器相关信息
      getTopInfoRect() {
        this._tGetRect('#top-info').then((res) => {
          if (!res) {
            setTimeout(() => {
              this.getTopInfoRect()
            }, 50)
            return
          }
          this.topInfo.height = res.height
        })
      },
      // 处理页面滚动事件
      handlePageScroll(scrollTop) {
        console.log(scrollTop);
        if (this.prevScrollTop > scrollTop) {
         
        // 内容下滑，即手指从下往上滚
         this.topInfoTranslateY = 0
        } else {
        // 内容上滑，即手指从上往下滚
          if (scrollTop > this.topInfo.height) {
            this.topInfoTranslateY = this.topInfo.height
          }
      
        }
        
        this.prevScrollTop = scrollTop
      },
    }
  }
</script>

<style lang="scss" scoped>
  .template-details{
  }
  .tn-tabbar-height {
  	min-height: 20rpx;
  	height: calc(40rpx + env(safe-area-inset-bottom) / 2);
  }
  
  /* 胶囊*/
  .tn-custom-nav-bar__back {
    width: 100%;
    height: 100%;
    position: relative;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    box-sizing: border-box;
    background-color: rgba(0, 0, 0, 0.15);
    border-radius: 1000rpx;
    border: 1rpx solid rgba(255, 255, 255, 0.5);
    color: #FFFFFF;
    font-size: 18px;
    
    .icon {
      display: block;
      flex: 1;
      margin: auto;
      text-align: center;
    }
    
    &:before {
      content: " ";
      width: 1rpx;
      height: 110%;
      position: absolute;
      top: 22.5%;
      left: 0;
      right: 0;
      margin: auto;
      transform: scale(0.5);
      transform-origin: 0 0;
      pointer-events: none;
      box-sizing: border-box;
      opacity: 0.7;
      background-color: #FFFFFF;
    }
  }
  
  /* 轮播视觉差 start */
  .card-swiper {
    height: 935rpx !important;
  }
    
  .card-swiper swiper-item {
    width: 750rpx !important;
    left: 0rpx;
    box-sizing: border-box;
    // padding: 0rpx 30rpx 90rpx 30rpx;
    overflow: initial;
  }
    
  .card-swiper swiper-item .swiper-item {
    width: 100%;
    display: block;
    height: 100%;
    transform: scale(1);
    transition: all 0.2s ease-in 0s;
    overflow: hidden;
  }
    
  .card-swiper swiper-item.cur .swiper-item {
    transform: none;
    transition: all 0.2s ease-in 0s;
  }
  
  .image-banner{
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .image-banner image{
    width: 100%;
    height: 100%;
  }
  
  /* 轮播指示点 start*/
  .indication{
    z-index: 9999;
    width: 100%;
    height: 36rpx;
    position: absolute;
    display:flex;
    flex-direction:row;
    align-items:center;
    justify-content:center;
  }
  
  .spot{
    background-color: #FFFFFF;
    opacity: 0.6;
    width: 10rpx;
    height: 10rpx;
    border-radius: 20rpx;
    top: -60rpx;
    margin: 0 8rpx !important;
    position: relative;
  }
  
  .spot.active{
    opacity: 1;
    width: 30rpx;
    background-color: #FFFFFF;
  }
  
  /* 间隔线 start*/
  .tn-strip-bottom-min {
    width: 100%;
    border-bottom: 1rpx solid #F8F9FB;
  }
  
  /* 间隔线 start*/
  .tn-strip-bottom {
   width: 100%;
   border-bottom: 20rpx solid rgba(241, 241, 241, 0.8);
  }
   /* 间隔线 end*/
  
  /* 底部*/
  .details-footerfixed {
    position: fixed;
    background-color: rgba(255,255,255,0.5);
    box-shadow: 0rpx 0rpx 30rpx 0rpx rgba(0, 0, 0, 0.07);
    bottom: 0;
    width: 100%;
    transition: all 0.25s ease-out;
    will-change: transform;
    z-index: 100;
  }
  
  
  /* 内容图 start */
  .content-backgroup {
    z-index: -1;
  
    .backgroud-image {
      width: 100%;
    }
  }
  /* 内容图 end */
 
  
  /* 图标容器12 start */
  .icon12 {
    &__item {
      background-color: #FFFFFF;
      border-radius: 10rpx;
      padding: 30rpx;
      margin: 20rpx 10rpx;
      transform: scale(1);
      transition: transform 0.3s linear;
      transform-origin: center center;
  
      &--icon {
        width: 60rpx;
        height: 60rpx;
        font-size: 28rpx;
        border-radius: 50%;
        border: 1rpx solid #E6E6E6;
        position: relative;
        z-index: 1;
      }
    }
  }
  
  /* 图标容器15 start */
  .icon15 {
    &__item {
      background-color: #FFFFFF;
      border-radius: 10rpx;
      padding: 30rpx;
      margin: 20rpx 10rpx;
      transform: scale(1);
      transition: transform 0.3s linear;
      transform-origin: center center;
  
      &--icon {
        width: 60rpx;
        height: 60rpx;
        font-size: 32rpx;
        border-radius: 50%;
        position: relative;
        padding: 10rpx;
        z-index: 1;
      }
    }
  }
</style>
