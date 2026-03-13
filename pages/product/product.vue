<template>
  <view class="template-product tn-safe-area-inset-bottom">
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
    
    <view class="" :style="{paddingTop: vuex_custom_bar_height + 20 + 'px'}">
      
      <view class="tn-search-fixed" style="background-color: #FFFFFF;">
        <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-margin" :style="{paddingTop: vuex_custom_bar_height + 'px'}">
          
          <view class="justify-content-item align-content-item" style="width: 100vw;">
            <view class="tn-flex tn-flex-col-center" style="border-bottom: 1rpx solid #E6E6E6;padding: 10rpx 20rpx 20rpx 0rpx;width: 90%;">
              <text class="tn-icon-search justify-content-item tn-padding-right-xs tn-color-gray tn-text-lg"></text>
              <input class="justify-content-item" placeholder="搜索时尚.." name="input" placeholder-style="color:#AAAAAA" style="width: 90%;"></input>
            </view>
          </view>
          
          <view class="align-content-item">
            <view class="justify-content-item tn-text-center">
              <tn-button :plain="true" shape="round" backgroundColor="#E6E6E6" padding="20rpx 20rpx" width="150rpx" @tap="">
                <text class="tn-color-gray">搜 索</text>
              </tn-button>
      
            </view>
          </view>
        </view>
      </view>
      
      <!-- 品牌商品 start-->
      <view class="tn-flex tn-flex-wrap tn-margin-left-sm tn-margin-bottom-lg tn-margin-right-sm" style="margin-top: 120rpx;">
        <block v-for="(item, index) in content" :key="index">
          <view class="" style="width: 50%;" @click="tn('/productPages/details')">
            <view class="tn-product-content__wrap tn-padding-bottom-lg">
              <view class="image-pic" :style="'background-image:url(' + item.mainImage + ')'">
                <view class="image-product">
                </view>
              </view> 
              
              <view class="tn-product-content__label tn-text-justify tn-padding-top-sm tn-padding-bottom-xs">
                <text class="tn-product-content__label__desc">{{ item.desc }}</text>  
              </view>
              
              <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-padding-bottom-sm">
                <view class="justify-content-item tn-flex tn-flex-col-center" style="margin-left: -6rpx;color: #3e4864;">
                  <text class="tn-text-xl">￥</text>
                  <text class="tn-padding-right-sm tn-text-xl">{{ item.price }}</text>
                  <!-- <text class="tn-color-gray tn-text-sm"> 66 人购买</text> -->
                </view>
                <view class="justify-content-item tn-flex tn-flex-col-center">
                  <tn-button size="sm" shape="icon" backgroundColor="#3e486400" fontColor="#3e4864" padding="10rpx 0 0 0" shadow>
                    <text class="tn-icon-buy tn-text-lg"></text>
                  </tn-button>
                </view>
              </view>
            </view>
          </view>
        </block>
      </view>
      <!-- 品牌商品 end-->
      
      
    </view>
    

    <view class='tn-tabbar-height'></view>
    
  </view>
</template>

<script>
  export default {
    name: 'Product',
    data(){
      return {
        content: [
          {
            price:'129',
            desc: '白色T-shirt和很想你',
            mainImage: 'https://cdn.nlark.com/yuque/0/2023/jpeg/280373/1683907347081-assets/web-upload/55d51df3-2f84-47d0-9bd9-82e4fbd17b3d.jpeg',
          },
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
          }
        ],
      }
    },

    methods: {
      
      // 跳转
      tn(e) {
      	uni.navigateTo({
      		url: e,
      	});
      }
      
    }
  }
</script>

<style lang="scss" scoped>
  .template-product{
    max-height: 100vh;
  }
  
  .tn-search-fixed{
    position: fixed;
    top: 0rpx;
    width: 100%;
    transition: all 0.25s ease-out;
    z-index: 1;
  }
  
  /* 阴影 start*/
  .home-shadow {
    border-radius: 15rpx;
    box-shadow: 0rpx 0rpx 50rpx 0rpx rgba(0, 0, 0, 0.07);
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
  
  /* 商家商品 start*/
  .tn-product-content {
    &__wrap {
      // box-shadow: 0rpx 0rpx 50rpx 0rpx rgba(0, 0, 0, 0.07);
      // border-radius: 20rpx;
      margin: 15rpx;
    }
    
    &__info {
      &__btn {
        margin-right: -12rpx;
        opacity: 0.5;
      }
    }
    
    &__label {
      
      &__desc {
        line-height: 35rpx;
      }
    }
  }
  
  .image-product{
    padding: 205rpx 0rpx;
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
  
  /* 商家商品 end*/
  
</style>