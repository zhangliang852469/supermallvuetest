<template>
  <div class="recommend">
    <div v-for="(item,index) in recommends" :key="index" class="recommend-item">
      <a :href="item.link"></a>
      <img :src="item.image">
      <div>{{item.title}}</div>
    </div>
  </div>
</template>

<script>
    export default {
        name: "RecommendView",
        props: {
            recommends: {
                type: Array,
                default() {
                    return [];
                }
            }
        }
    }
</script>

<style scoped>
  .recommend {
    display: flex;
    text-align: center;
    width: 100%;
    font-size: 12px;
    padding: 10px 0 20px;
    border-bottom: 10px solid #eee;
  }
  .recommend-item {
    flex: 1;
  }
  .recommend-item img {
    width: 70px;
    height: 70px;
    margin-bottom: 10px;
  }
</style>
