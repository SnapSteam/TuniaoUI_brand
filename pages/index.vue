<template>
  <view class="start-index">
    <view v-if="tabberPageLoadFlag[0]" :style="{display: currentIndex === 0 ? '' : 'none'}">
      <scroll-view class="custom-tabbar-page" scroll-y enable-back-to-top @scrolltolower="tabbarPageScrollLower">
        <home ref="home"></home>
      </scroll-view>
    </view>
    <view v-if="tabberPageLoadFlag[1]" :style="{display: currentIndex === 1 ? '' : 'none'}">
      <scroll-view class="custom-tabbar-page" scroll-y enable-back-to-top @scrolltolower="tabbarPageScrollLower">
        <product ref="product"></product>
      </scroll-view>
    </view>
    <view v-if="tabberPageLoadFlag[2]" :style="{display: currentIndex === 2 ? '' : 'none'}">
      <scroll-view class="custom-tabbar-page" scroll-y enable-back-to-top @scrolltolower="tabbarPageScrollLower">
        <cart ref="cart"></cart>
      </scroll-view>
    </view>
    <view v-if="tabberPageLoadFlag[3]" :style="{display: currentIndex === 3 ? '' : 'none'}">
      <scroll-view class="custom-tabbar-page" scroll-y enable-back-to-top @scrolltolower="tabbarPageScrollLower">
        <mine ref="mine"></mine>
      </scroll-view>
    </view>
    
    <tn-tabbar
      v-model="currentIndex"
      :list="tabbarList"
      activeColor="#838383"
      inactiveColor="#AAAAAA"
      activeIconColor="#3e4864"
      :animation="true"
      :safeAreaInsetBottom="true"
      @change="switchTabbar"
    ></tn-tabbar>
  </view>
</template>

<script>
  import Home from './home/home.vue'
  import Product from './product/product.vue'
  import Cart from './cart/cart.vue'
  import Mine from './mine/mine.vue'
  
  export default {
    components: {
      Home,
      Product,
      Cart,
      Mine
    },
    data() {
      return {
        // 底部tabbar菜单数据
        tabbarList: [
          {
            title: '首页',
            /* activeIcon: '/static/tabbar/home_tnnew.png',
            inactiveIcon: '/static/tabbar/home_tn.png' */
            activeIcon: 'home-in',
            inactiveIcon: 'home-in'
          },
          {
            title: '全部',
            /* activeIcon: '/static/tabbar/preferred_tnnew.png',
            inactiveIcon: '/static/tabbar/preferred_tn.png', */
            activeIcon: 'search-menu',
            inactiveIcon: 'search-menu'
          },
          {
            title: '购物车',
            /* activeIcon: '/static/tabbar/circle_tnnew.png',
            inactiveIcon: '/static/tabbar/circle_tn.png' */
            activeIcon: 'basket',
            inactiveIcon: 'basket',
            // count: 12
          },
          {
            title: '我的',
            /* activeIcon: '/static/tabbar/mine_tnnew.png',
            inactiveIcon: '/static/tabbar/mine_tn.png' */
            activeIcon: 'my-simple',
            inactiveIcon: 'my-simple'
          }
        ],
        // tabbar当前被选中的序号
        currentIndex: 0,
        // 自定义底栏对应页面的加载情况
        tabberPageLoadFlag: []
      }
    },
    onLoad(options) {
      const index = Number(options.index || 0)
      // 根据底部tabbar菜单列表设置对应页面的加载情况
      this.tabberPageLoadFlag = this.tabbarList.map((item, tabbar_index) => {
        return index === tabbar_index
      })
      this.switchTabbar(index)
    },
    methods: {
      // 切换导航
      switchTabbar(index) {
        this._switchTabbarPage(index)
      },
      
      // 导航页面滚动到底部
      tabbarPageScrollLower(e) {

      },
      
      // 切换导航页面
      _switchTabbarPage(index) {
        wx.vibrateShort();
        const selectPageFlag = this.tabberPageLoadFlag[index]
        if (selectPageFlag === undefined) {
          return
        }
        if (selectPageFlag === false) {
          this.tabberPageLoadFlag[index] = true
        }
        this.currentIndex = index
      }
    }
  }
</script>

<style lang="scss" scoped>
</style>
