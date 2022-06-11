<template>
  <div class="header">
    <div class="header-inner">
      <div class="menu-ttl-wrap">
        <div class="menu box-shadow" id="menu">
          <span class="menu__line--top"></span>
          <span class="menu__line--middle"></span>
          <span class="menu__line--bottom"></span>
        </div>
        <h1 class="ttl">Rese</h1>
      </div>
    </div>
  </div>
</template>

<style scoped>
.header {
  width: 90%;
  margin: 0 auto;
  padding: 40px 0;
}

.header-inner {
  display: flex;
  align-items: center;
}

.menu-ttl-wrap {
  display: flex;
  align-items: center;
}

.menu {
  display: inline-block;
  width: 30px;
  height: 30px;
  cursor: pointer;
  position: relative;
  background-color: #305dff;
  padding: 10px;
  border-radius: 5px;
  z-index: 1;
}

.menu__line--top {
  width: 30%;
  top: 15px;
}

.menu__line--middle {
  width: 50%;
  top: 23.7px;
}

.menu__line--bottom {
  width: 20%;
  bottom: 15px;
}

.menu__line--top,
.menu__line--middle,
.menu__line--bottom {
  display: inline-block;
  height: 1px;
  background-color: #fff;
  position: absolute;
  transition: 0.5s;
}

.menu.open span:nth-of-type(1) {
  top: 25px;
  width: 60%;
  transform: rotate(45deg);
}

.menu.open span:nth-of-type(2) {
  opacity: 0;
}

.menu.open span:nth-of-type(3) {
  top: 25px;
  width: 60%;
  transform: rotate(-45deg);
}

.ttl {
  color: #305dff;
  font-weight: bold;
  font-size: 34px;
  margin-left: 20px;
}

.box-shadow {
  box-shadow: 2px 2px 4px 1px #888;
}

@media screen and (max-width: 768px) {
  .header-inner {
    display: block;
    align-items: normal;
  }
}
</style>
