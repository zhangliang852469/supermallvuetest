<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :banners="banners"/>
    <recommend-view :recommends="recommend"/>
    <feature-view/>
    <tab-control :titles="['流行', '新款', '精选']" class="tab-control"/>
    <ul>
      <li>李彪1</li>
      <li>李彪2</li>
      <li>李彪3</li>
      <li>李彪4</li>
      <li>李彪5</li>
      <li>李彪6</li>
      <li>李彪7</li>
      <li>李彪8</li>
      <li>李彪9</li>
      <li>李彪10</li>
      <li>李彪11</li>
      <li>李彪12</li>
      <li>李彪13</li>
      <li>李彪14</li>
      <li>李彪15</li>
      <li>李彪16</li>
      <li>李彪17</li>
      <li>李彪18</li>
      <li>李彪19</li>
      <li>李彪20</li>
      <li>李彪21</li>
            <li>李彪11</li>
      <li>李彪12</li>
      <li>李彪13</li>
      <li>李彪14</li>
      <li>李彪15</li>
      <li>李彪16</li>
      <li>李彪17</li>
      <li>李彪18</li>
      <li>李彪19</li>
      <li>李彪20</li>
      <li>李彪21</li>
            <li>李彪11</li>
      <li>李彪12</li>
      <li>李彪13</li>
      <li>李彪14</li>
      <li>李彪15</li>
      <li>李彪16</li>
      <li>李彪17</li>
      <li>李彪18</li>
      <li>李彪19</li>
      <li>李彪20</li>
      <li>李彪21</li>
    </ul>
  </div>

</template>

<script>
    import NavBar from "components/common/navbar/NavBar";

    import HomeSwiper from "./childComps/HomeSwiper";
    import RecommendView from "./childComps/RecommendView";
    import FeatureView from "./childComps/FeatureView";
    import TabControl from "components/content/tabControl/TabControl";

    import {getHomeMultidata} from "network/home";

    export default {
        name: "Home",
        components: {HomeSwiper, NavBar, RecommendView, FeatureView, TabControl},
        data() {
            return {
                banners: [],
                recommend: []
            }
        },
        created() {
            getHomeMultidata().then(res => {
                this.banners = res.data.banner.list;
                this.recommend = res.data.recommend.list
            })
        }
    }
</script>

<style scoped>
  .home-nav {
    background-color: var(--color-tint);
    color: #f6f6f6;
    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    z-index: 9;
  }
  #home {
    padding-top: 44px;
  }
  .tab-control {
    position: sticky;
    top: 44px;
  }
</style>
