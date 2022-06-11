<template>
  <div class="nav">
    <ul class="nav-list">
      <li class="nav-item">
        <button class="nav-btn">Home</button>
      </li>
      <li class="nav-item">
        <button class="nav-btn">Registration</button>
      </li>
      <li class="nav-item">
        <button class="nav-btn">User Login</button>
      </li>
      <li class="nav-item">
        <button class="nav-btn">Admin Login</button>
      </li>
      <li class="nav-item">
        <button class="nav-btn">Shop Login</button>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.nav {
  position: absolute;
  height: 100vh;
  width: 100%;
  left: -100%;
  background: #fff;
  transition: .7s;
  text-align: center;
  z-index: 1;
}
.nav-list {
  padding-top: 80px;
}
.nav-item {
  list-style-type: none;
  margin-top: 40px;
}
.nav-link {
  text-decoration: none;
  color: #305dff;
  font-size: 30px;
}

.nav-btn {
  border: none;
  color: #305dff;
  font-size: 30px;
  background-color: transparent;
  cursor: pointer;
}
</style>
