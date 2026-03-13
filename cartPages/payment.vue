<template>
  <view class="template-payment">
    <!-- 顶部自定义导航 -->
    <!-- <tn-nav-bar fixed alpha customBack>
      <view slot="back" class='tn-custom-nav-bar__back'
        @click="goBack">
        <text class='icon tn-icon-left-arrow'></text>
      </view>
    </tn-nav-bar> -->
    
    <!-- 顶部自定义导航 -->
    <tn-nav-bar fixed customBack :bottomShadow="false" backgroundColor="#FFFFFF">
      <view slot="back" class='tn-custom-nav-bar__back'
        @click="goBack">
        <text class='icon tn-icon-left-arrow'></text>
      </view>
      <view class="tn-flex tn-flex-col-center tn-flex-row-center ">
        <text class="tn-text-xl tn-color-black">订单支付</text>
      </view>
    </tn-nav-bar>
    
    
    <view class="" :style="{paddingTop: vuex_custom_bar_height + 20 + 'px'}">
      
      <view class="" @click="navAddress">
        <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-padding-top-xs tn-padding-bottom-xs">
          <view class="justify-content-item">
            <view class="tn-flex tn-flex-col-center tn-flex-row-left">
              <view class="tn-padding tn-color-black">
                <view class="tn-padding-right-sm tn-text-bold">
                  <text class="tn-text-xl">付衣衣</text>
                  <text class="tn-padding-left-sm tn-text-lg">183 6666 6666</text>
                </view>
                <view class="tn-padding-right tn-padding-top-xs tn-text-ellipsis tn-color-gray">
                  <text class="">广东省广州市番禺区祈福新邨129号</text>
                </view>
              </view>
            </view>
          </view>
          <view class="tn-flex justify-content-item tn-flex-row-center tn-padding-right-xs">
            <view class="tn-bg-gray--light tn-padding-xs tn-margin-sm tn-color-black tn-round">
              <text class="tn-icon-location-fill" style="font-size: 60rpx;"></text>
            </view>
          </view>
        </view>
      </view>
      
      <block v-for="(item, index) in content" :key="index">
        <view class="tn-flex tn-flex-col-top tn-margin">
          <view class="image-pic" :style="'background-image:url(' + item.mainImage + ')'" @click="tn('')">
            <view class="image-cart">
            </view>
          </view>
          <view class="tn-padding-left" style="width: 100%;">
            <view class="tn-flex tn-flex-row-between tn-flex-col-between tn-padding-top-lg">
              <view class="justify-content-item">
                <text class="tn-color-black clamp-text-1">{{ item.desc }}</text>
              </view>
            </view>
            <view class="tn-flex tn-flex-row-between tn-flex-col-between">
              <view class="justify-content-item tn-padding-top">
                <text class="tn-color-gray clamp-text-1">规格：S码，棕色</text>
              </view>
            </view>
            <view class="tn-flex tn-flex-row-between tn-flex-col-between tn-padding-top-sm">
              <view class="justify-content-item tn-padding-top-xs">
                <text class="tn-color-gray clamp-text-1">数量：X1</text>
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
      
      
      <view class="tabbar footerfixed tn-bg-gray--light">
        <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-padding-top-xs">
          <view class="justify-content-item tn-margin-top">
            <view class="tn-flex tn-flex-row-center tn-flex-col-center">
              <view class="tn-flex tn-flex-row-center tn-flex-col-center">
                <view class="tn-padding-right tn-padding-left tn-text-ellipsis">
                    <text class="tn-text-xxl">￥</text>
                    <text class="tn-text-xxl tn-padding-left-xs">1,920</text>
                </view>
              </view>
            </view>
          </view>
          <view class="justify-content-item tn-flex tn-flex-row-center tn-margin-top tn-padding-right">
            <view class="tn-flex-1 justify-content-item tn-margin-right-lg tn-text-center">
              <tn-button shape="round" :plain="true" backgroundColor="tn-bg-black" width="110%"  @click="tn('')">
                <text class="tn-color-black" hover-class="tn-hover" :hover-stay-time="150">
                  朋友代付
                </text>
              </tn-button>
            </view>
            <view class="tn-flex-1 justify-content-item tn-margin-right-sm tn-text-center">
              <tn-button shape="round" backgroundColor="tn-bg-black" width="110%"  @click="tn('')">
                <text class="tn-color-white" hover-class="tn-hover" :hover-stay-time="150">
                  立即支付
                </text>
              </tn-button>
            </view>
          </view>
        </view>
      </view>
      
      <view class='tn-tabbar-height'></view>
      
    </view>
  </view>
</template>

<script>
  import template_page_mixin from '@/libs/mixin/template_page_mixin.js'
  export default {
    name: 'TemplatePayment',
    mixins: [template_page_mixin],
    data(){
      return {
        content: [
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
          }
        ],
      }
    },
    methods: {
      // 收货地址
      navAddress() {
        uni.chooseAddress({
        })
      },
    }
  }
</script>

<style lang="scss" scoped>
  /* 胶囊*/
  .tn-custom-nav-bar__back {
    width: 60%;
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
  }
  
  /* 底部安全边距 start*/
  .tn-tabbar-height {
  	min-height: 120rpx;
  	height: calc(140rpx + env(safe-area-inset-bottom) / 2);
    height: calc(140rpx + constant(safe-area-inset-bottom));
  }
  
  /* 底部 start*/
  .footerfixed{
   position: fixed;
   width: 100%;
   bottom: 0;
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
