<template>
  <div class="search">
    <div class="search-inner box-shadow">
      <div class="search-form-inner">
        <div class="search-select-wrap">
        </div>
        <span class="partition">|</span>
        <div class="search-select-wrap">
        </div>
        <span class="partition">|</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.search {
  margin-left: auto;
  width: 50%
}
.search-inner {
  border-radius: 5px;
  width: 100%;
}
.search-form-inner {
    display: flex;
    align-items: center;
    background-color: #fff;
    border-radius: 5px;
    width: 100%;
}
.search-select-wrap {
  width: 25%;
  position: relative;
}
.partition {
  color: #ccc;
  font-size: 20px;
}
</style>
