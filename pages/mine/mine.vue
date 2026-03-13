<template>
  <view class="template-mine tn-safe-area-inset-bottom">
    
    <!-- 顶部自定义导航 -->
    <tn-nav-bar :isBack="false" :bottomShadow="false" backgroundColor="#FFFFFF00">
      <view class="custom-nav tn-flex tn-flex-col-center tn-flex-row-left">
        <view class="custom-nav__logo" @click="tn('')">
          <view class="tn-icon-menu-grille tn-color-white"></view>
        </view>
        <!-- <view class="tn-flex-col-center tn-flex-row-center tn-text-lg" style="margin-left: 25vw;">
          <text class="tn-text-xxl tn-color-white">TN Fashion</text>
        </view> -->
      </view>
    </tn-nav-bar>

 
    <view class="top-backgroup">
      <image src='https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1684203031924-assets/web-upload/fbb2259d-5f06-43df-824a-8007c5953c82.jpeg' mode='widthFix' class='backgroud-image'></image>
      <!-- <image src='https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1684203031951-assets/web-upload/d5b4e2a6-8548-40ee-a6e3-f2b47913814d.jpeg' mode='widthFix' class='backgroud-image'></image> -->
    </view>
    
    <view class="" :style="{paddingTop: vuex_custom_bar_height + 25 + 'px'}">
      
      <view class="tn-margin-left tn-margin-right"  style="margin-top: -465rpx;">
      <!-- 图标logo/头像 -->
      <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-margin-bottom">
        <view class="justify-content-item">
          <view class="tn-flex tn-flex-col-center tn-flex-row-left">
            
            <view class="tn-padding-right">
              <view class="tn-padding-right tn-padding-left-sm">
                <text class="tn-color-white tn-text-bold" style="font-size: 50rpx;">不许凶我吖</text>
              </view>
              <view class="tn-padding-right tn-padding-top-sm tn-padding-left-sm tn-text-ellipsis" @click="copyUid">
                <text class="tn-color-gray">Uid: 10262008</text>
                <text class="tn-color-white tn-padding-left-xs tn-text-sm tn-icon-copy"></text>
              </view>
            </view>

          </view>
        </view>
        <view class="justify-content-item tn-margin-right-sm" @click="tn('/minePages/set')">
          <view class="logo-pic">
            <view class="logo-image">
              <view class="tn-shadow-blur" style="background-image:url('https://cdn.nlark.com/yuque/0/2022/jpeg/280373/1664005699053-assets/web-upload/8645ea3a-e0a9-4422-8364-cc5ede305c9f.jpeg');width: 120rpx;height: 120rpx;background-size: cover;overflow: hidden;">
              </view>
            </view>
          </view>
        </view>
      </view>
      
      <!-- 用户没有授权，则显示这个授权按钮，自行看着需不需要用就行-->
     <!-- <view class="tn-flex tn-flex-row-between tn-padding-bottom tn-padding-top-lg" @click="tn('/minePages/login')">
        <view class="tn-flex-1 justify-content-item tn-margin-xs tn-text-center">
          <tn-button shape="round" backgroundColor="#FFFFFF" fontColor="#1D2541" padding="20rpx 0" width="40%">
            <text class="tn-icon-wechat tn-padding-right-xs tn-text-xl"></text>
            <text class="">授权登录</text>
          </tn-button>
        </view>
      </view> -->
      
        
      </view>
      

      <!-- 方式12 start-->
      <view class="tn-padding-bottom-sm tn-bg-white tn-margin-left tn-margin-right" style="padding-top: 140rpx;">
        
        <view class="tn-flex tn-flex-row-between tn-padding-bottom tn-bg-white">
          <view class="tn-padding-xs" @click="tn('/minePages/order')">
            <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
              <view class="icon12__item--icon tn-flex tn-flex-row-center tn-flex-col-center">
                <view class="tn-icon-order-fill tn-color-wallpaper"></view>
              </view>
              <view class="tn-text-center">
                <text class="tn-text-ellipsis">全部订单</text>
              </view>
            </view>
          </view>
          <view class="tn-padding-xs" @click="tn('/minePages/vip')">
            <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
              <view class="icon12__item--icon tn-flex tn-flex-row-center tn-flex-col-center ">
                <view class="tn-icon-vip-fill tn-color-wallpaper"></view>
              </view>
              <view class="tn-text-center">
                <text class="tn-text-ellipsis">会员权益</text>
              </view>
            </view>
          </view>
          <view class="tn-padding-xs" @click="tn('/minePages/set')">
            <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
              <view class="icon12__item--icon tn-flex tn-flex-row-center tn-flex-col-center">
                <view class="tn-icon-identity-fill tn-color-wallpaper"></view>
              </view>
              <view class="tn-text-center">
                <text class="tn-text-ellipsis">个人信息</text>
              </view>
            </view>
          </view>
          <view class="tn-padding-xs" @click="tn('/minePages/help')">
            <view class="tn-flex tn-flex-direction-column tn-flex-row-center tn-flex-col-center">
              <view class="icon12__item--icon tn-flex tn-flex-row-center tn-flex-col-center">
                <view class="tn-icon-help-fill tn-color-wallpaper"></view>
              </view>
              <view class="tn-text-center">
                <text class="tn-text-ellipsis">常见问题</text>
              </view>
            </view>
          </view>
        </view>
        
      </view>
      
      <view class="tn-strip-bottom"></view>

      <!-- 更多信息-->
      <view class="tn-padding-top-sm tn-padding-bottom-sm">
        <tn-list-cell :hover="true" :unlined="true" :radius="true" :fontSize="30" @click="copySource">
          <view class="tn-flex tn-flex-col-center">
            <view
              class="icon1__item--icon tn-flex tn-flex-row-center tn-flex-col-center" style="color: #1d2541;">
              <view class="tn-icon-plane"></view>
            </view>
            <view class="tn-margin-left-sm tn-flex-1">开源地址</view>
            <view class="tn-color-gray tn-icon-right"></view>
          </view>
        </tn-list-cell>
        <tn-list-cell :hover="true" :unlined="true" :radius="true" :fontSize="30" @click="tn('/minePages/public')">
          <view class="tn-flex tn-flex-col-center">
            <view
              class="icon1__item--icon tn-flex tn-flex-row-center tn-flex-col-center" style="color: #1d2541;">
              <view class="tn-icon-bookmark"></view>
            </view>
            <view class="tn-margin-left-sm tn-flex-1">关注我们</view>
            <view class="tn-color-gray tn-icon-right"></view>
          </view>
        </tn-list-cell>
      </view>
      
      <view class="tn-strip-bottom"></view>
      
      <view class="tn-margin-bottom-lg tn-padding-top-sm tn-padding-bottom-sm">
        <tn-list-cell :hover="true" :unlined="true" :radius="true" :fontSize="30">
          <button class="tn-flex tn-flex-col-center tn-button--clear-style" open-type="contact">
            <view
              class="icon1__item--icon tn-flex tn-flex-row-center tn-flex-col-center" style="color: #1d2541;">
              <view class="tn-icon-service"></view>
            </view>
            <view class="tn-flex tn-flex-row-between" style="width: 100%;">
              <view class="tn-margin-left-sm">专属客服</view>
              <view class="tn-color-gray tn-icon-right"></view>
            </view>
          </button>
        </tn-list-cell>
        <tn-list-cell :hover="true" :unlined="true" :radius="true" :fontSize="30">
          <button class="tn-flex tn-flex-col-center tn-button--clear-style" open-type="feedback">
            <view
              class="icon1__item--icon tn-flex tn-flex-row-center tn-flex-col-center" style="color: #1d2541;">
              <view class="tn-icon-tip"></view>
            </view>
            <view class="tn-flex tn-flex-row-between" style="width: 100%;">
              <view class="tn-margin-left-sm">问题反馈</view>
              <view class="tn-color-gray tn-icon-right"></view>
            </view>
          </button>
        </tn-list-cell>
        <tn-list-cell :hover="true" :unlined="true" :radius="true" :fontSize="30" @click="callPhoneNumber" data-number="18266666666">
          <view class="tn-flex tn-flex-col-center">
            <view
              class="icon1__item--icon tn-flex tn-flex-row-center tn-flex-col-center" style="color: #1d2541;">
              <view class="tn-icon-tel-circle"></view>
            </view>
            <view class="tn-margin-left-sm tn-flex-1">技术热线</view>
            <view
              class="tn-margin-left-sm tn-color-wallpaper tn-text-sm tn-padding-left-xs tn-padding-right-xs tn-bg-gray--light tn-round">
              188****8888</view>
          </view>
        </tn-list-cell>
      </view>

    </view>
    
    <view class="tn-text-center tn-margin-top-xl tn-padding-bottom-xl" style="opacity: 0.5;">
    	<view @click="navTuniaoUI">
        <text class="">—</text>
        <text class="tn-padding-xs" style="color: #1d2541;">图鸟科技</text>
        <text class="tn-padding-xs">提供技术支持</text>
        <text class="">—</text>
      </view>
    </view>
   

    <view class='tn-tabbar-height'></view>

  </view>
</template>

<script>
  export default {
    name: 'Mine',
    data() {
      return {
      }
    },
    methods: {
      
      // 跳转
      tn(e) {
        uni.navigateTo({
          url: e,
        });
      },
      
      // 跳转到图鸟UI
      navTuniaoUI() {
        uni.navigateToMiniProgram({
          appId: 'wxf3d81a452b88ff4b'
        })
      },
      
      // 收货地址
      navAddress() {
        uni.chooseAddress({
        })
      },
      
      //拨打固定电话
      callPhoneNumber() {
        uni.makePhoneCall({
          phoneNumber: "18219128888",
        });
      },
      // 复制id
      copyUid() {
        wx.vibrateShort();
        uni.setClipboardData({
          data: "10262008",
        })
      },
      // 复制开源地址
      copySource() {
        wx.vibrateShort();
        uni.setClipboardData({
          data: "https://ext.dcloud.net.cn/publisher?id=356088",
        })
      },
    }
  }
</script>

<style lang="scss" scoped>
  .template-mine{
    max-height: 100vh;
  }
  /* 底部安全边距 start*/
  .tn-tabbar-height {
  	min-height: 120rpx;
  	height: calc(140rpx + env(safe-area-inset-bottom) / 2);
    height: calc(140rpx + constant(safe-area-inset-bottom));
  }
  
  .tn-color-wallpaper{
    color: #1D2541;
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
  

  /* 顶部背景图 start */
  .top-backgroup {
    height: 475rpx;
    z-index: -1;
  
    .backgroud-image {
      width: 100%;
      height: 475rpx;
      background-color: #1D2541;
      // z-index: -1;
    }
  }
  /* 顶部背景图 end */

  

  /* 用户头像 start */
  .logo-image {
    width: 120rpx;
    height: 120rpx;
    position: relative;
    overflow: hidden;
    border-radius: 50%;
  }

  .logo-pic {
    background-size: cover;
    background-repeat: no-repeat;
    // background-attachment:fixed;
    background-position: top;
    border: 6rpx solid rgba(255,255,255,0.85);
    box-shadow: 0rpx 0rpx 80rpx 0rpx rgba(0, 0, 0, 0.15);
    border-radius: 50%;
    overflow: hidden;
    // background-color: #FFFFFF;
  }

  

  /* 图标容器12 start */
  .icon12 {
    &__item {
      width: 30%;
      background-color: #FFFFFF;
      border-radius: 10rpx;
      padding: 30rpx;
      margin: 20rpx 10rpx;
      transform: scale(1);
      transition: transform 0.3s linear;
      transform-origin: center center;

      &--icon {
        width: 100rpx;
        height: 100rpx;
        font-size: 40rpx;
        border-radius: 50%;
        border: 1rpx solid #E6E6E6;
        margin-bottom: 18rpx;
        position: relative;
        z-index: 1;
      }
    }
  }
  
  /* 图标容器1 start */
  .icon1 {
    &__item {
      // width: 30%;
      background-color: #FFFFFF;
      border-radius: 10rpx;
      padding: 30rpx;
      margin: 20rpx 10rpx;
      transform: scale(1);
      transition: transform 0.3s linear;
      transform-origin: center center;
  
      &--icon {
        width: 50rpx;
        height: 50rpx;
        font-size: 40rpx;
        border-radius: 50%;
        position: relative;
        z-index: 1;
      }
    }
  }
  
  /* 图标容器1 end */
  
  /* 间隔线 start*/
  .tn-strip-bottom {
   width: 100%;
   border-bottom: 20rpx solid rgba(241, 241, 241, 0.8);
  }
  
</style>
