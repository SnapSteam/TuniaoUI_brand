<template>
  <view class="template-cart tn-safe-area-inset-bottom">
    
    <!-- 顶部自定义导航 -->
    <tn-nav-bar :isBack="false" :bottomShadow="false" backgroundColor="#FFFFFF">
      <view class="custom-nav tn-flex tn-flex-col-center tn-flex-row-left">
        <view class="custom-nav__logo" @click="tn('')">
          <view class="tn-icon-menu-grille tn-color-black"></view>
        </view>
        <view class="tn-flex-col-center tn-flex-row-center tn-text-lg" style="margin-left: 25vw;">
          <text class="tn-text-xxl tn-color-black">TN Fashion</text>
        </view>
      </view>
    </tn-nav-bar>

    <view class="" :style="{paddingTop: vuex_custom_bar_height + 'px'}" >
      <view class="" style="padding: 40rpx 0 310rpx 0;">
        <block v-for="(item, index) in content" :key="index">
          <view class="tn-flex tn-flex-col-top tn-margin tn-padding-xs">
            <view class="tn-flex tn-flex-col-center">
              <view class="tn-padding-right">
                <view class="tn-icon-circle tn-text-xl tn-color-gray"></view>
              </view>
              <view class="image-pic" :style="'background-image:url(' + item.mainImage + ')'" @click="tn('/productPages/details')">
                <view class="image-cart">
                </view>
              </view>
            </view>
            <view class="tn-padding-left-sm" style="width: 90%;">
              <view class="tn-flex tn-flex-row-between tn-flex-col-between tn-padding-top-lg">
                <view class="justify-content-item">
                  <text class="tn-color-black clamp-text-1">{{ item.desc }}</text>
                </view>
                <view class="justify-content-item">
                  <text class="tn-color-gray--disabled tn-icon-close"></text>
                </view>
              </view>
              <view class="tn-flex tn-flex-row-between tn-flex-col-between">
                <view class="justify-content-item tn-padding-top-xs">
                  <text class="tn-color-gray clamp-text-1">规格：S码，棕色</text>
                </view>
              </view>
              <view class="tn-flex tn-flex-row-between tn-flex-col-between tn-padding-top-lg">
                <view class="justify-content-item" style="opacity: 0.6;">
                  <tn-number-box v-model="value" :min="1" :max="9" :disabledInput="true"></tn-number-box>
                </view>
                <view class="justify-content-item tn-padding-top-xs tn-color-black">
                  <text class="clamp-text-1">￥</text>
                  <text class="clamp-text-1 tn-text-lg">{{ item.price }}</text>
                </view>
              </view>
              <view class="tn-flex tn-flex-row-between tn-flex-col-between">
                
              </view>
            </view>
          </view>
        
        </block>
        
      </view>
    </view>
    
    <view class="tabbar footerfixed tn-bg-gray--light">
      <view class="tn-flex tn-flex-row-between tn-flex-col-center">
        <view class="justify-content-item tn-margin-top">
          <view class="tn-flex tn-flex-row-center tn-flex-col-center">
            <view class="tn-flex tn-flex-row-center tn-padding-right tn-padding-left">
              <text class="tn-icon-circle tn-text-xl tn-color-gray"></text> 
              <text class="tn-padding-left-xs tn-color-gray">全选</text>
            </view>
            <view class="tn-flex tn-flex-row-center tn-flex-col-center">
              <view class="tn-padding-right tn-text-ellipsis">
                <view class="tn-padding-right tn-padding-left-sm">
                  <text>总价：￥</text>
                  <text class="tn-text-lg">1,920</text>
                </view>
              </view>
            </view>
          </view>
        </view>
        <view class="justify-content-item tn-flex-row-center tn-margin-top tn-padding-right">
          <tn-button shape="round" backgroundColor="tn-bg-black" width="100%" @click="tn('/cartPages/payment')">
            <text class="tn-color-white" hover-class="tn-hover" :hover-stay-time="150">
              立即结算
            </text>
          </tn-button>
        </view>
      </view>
    </view>
   
    

  </view>
</template>

<script>
  export default {
    name: 'Cart',
    data(){
      return {
        content: [
          {
            price:'288',
            desc: '橙色卫衣和榨芒果汁',
            mainImage: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683906320444-assets/web-upload/efc56953-c719-46ec-ad24-1f207516ca9d.jpeg',
          },
          {
            price:'299',
            desc: '淡红外套和白色衬衫',
            mainImage: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683905799657-assets/web-upload/7e3e822c-e054-4319-9b1f-5db58be0023e.jpeg',
          },
          {
            price:'199',
            desc: '条纹V衫和单肩背包',
            mainImage: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683907347231-assets/web-upload/0f7ae432-0a19-44fb-ba99-47fe41537f11.jpeg',
          },
          {
            price:'389',
            desc: '黑色皮套和黑色书包',
            mainImage: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683906918806-assets/web-upload/a9f24fd8-3fde-4e96-a0c5-773cb10829b1.jpeg',
          },
          {
            price:'298',
            desc: '全身风衣和蓝色衬衫',
            mainImage: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683905940454-assets/web-upload/4a4d5700-d88a-47ab-ab5e-fbbb50609528.jpeg',
          },
          {
            price:'368',
            desc: '牛仔外套和粉色帽子',
            mainImage: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683906549731-assets/web-upload/112734a9-fec7-427f-901a-bed1a34dacd0.jpeg',
          },
          {
            price:'129',
            desc: '白色T-shirt和很想你',
            mainImage: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683907347081-assets/web-upload/55d51df3-2f84-47d0-9bd9-82e4fbd17b3d.jpeg',
          }
        ],
      }
    },
    methods: {
      // 跳转
      tn(e) {
        // 短震动跳转
        wx.vibrateShort();
      	uni.navigateTo({
      		url: e,
      	});
      },
    }
  }
</script>

<style lang="scss" scoped>
  .template-cart{
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
  
  /* 底部 start*/
  .footerfixed{
   position: fixed;
   width: 100%;
   bottom: calc(100rpx + env(safe-area-inset-bottom) / 2);
   z-index: 999;
   // background-color: rgba(255,255,255,1);
   // box-shadow: 0rpx 0rpx 30rpx 0rpx rgba(0, 0, 0, 0.07);
  }
  
  .tabbar {
    align-items: center;
    min-height: 130rpx;
  	padding: 0;
  	height: calc(130rpx + env(safe-area-inset-bottom) / 2);
  	padding-bottom: calc(30rpx + env(safe-area-inset-bottom) / 2);
    padding-left: 10rpx;
    padding-right: 10rpx;
  }
 
 
  .image-cart{
    width: 200rpx;
    height: 250rpx;
    font-size: 16rpx;
    font-weight: 300;
    position: relative;
  }
  .image-pic{
    background-size: cover;
    background-repeat:no-repeat;
    // background-attachment:fixed;
    background-position:top;
    // border-radius: 15rpx 15rpx 0 0;
  }
  
</style>
