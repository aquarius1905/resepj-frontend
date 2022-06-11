<template>
  <div class="shop">
    <Header></Header>
    <Search></Search>
    <div class="shop-list">
      <div v-for="(item, index) in shopItems" :key="index" class="shop-card box-shadow">
        <div class="card-img-container">
        </div>
        <div class="card-content">
          <h2 class="card-ttl">{{ item.name }}</h2>
          <div class="card-tag-container">
            <p class="shop-area">#{{ item.area }}</p>
            <p class="shop-genre">#{{ item.genre }}</p>
          </div>
          <div class="card-btn-container">
            <a href="" class="btn">詳しく見る</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      shopItems: [],
    };
  },
  methods: {
    async getShops() {//全ての投稿を取得
      this.shopItems.splice(0);
      const { data } = await this.$axios.get('/api/shops');
      for (const shopData of data.items) {
        console.log(shopData);
          const shopItem = {
            name: shopData.name,
            area: shopData.area.name,
            genre: shopData.genre.name
          };
        this.shopItems.push(shopItem);
      }
    },
  },
  created() {
    //全ての飲食店を取得
    this.getShops();
  },
};
</script>

<style scoped>
.shop-list {
  display: flex;
  justify-content: flex-start;
  flex-wrap: wrap;
  margin: 0 auto;
  max-width: 90%;
}

.shop-card {
  background-color: #fff;
  border-radius: 10px;
  width: calc((100% - 20px * 3) / 4);
  margin: 0 20px 40px 0;
}

.shop-card:nth-of-type(4n) {
  margin-right: 0;
}

.card-img-container {
  display: inline-block;
  position: relative;
}

.card-content {
  padding: 25px;
}
.card-ttl {
  font-size: 20px;
  margin-bottom: 20px;
}
.card-tag-container {
  display: flex;
  margin-bottom: 20px;
}
.card-btn-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>