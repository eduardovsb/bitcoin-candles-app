<template>
  <div id="header">
    <img :src="logo" alt="Bitcoin logo" />
    <span>Bitcoin Candle App</span>
  </div>
</template>

<script lang="ts">
import { Vue } from 'vue-class-component';
import logo from '../assets/logo.png';

export default class Header extends Vue {
  get logo() {
    return logo;
  }
}
</script>

<style>
#header {
  background-image: linear-gradient(to right, #4d05e8, #4871f7);
  padding: 30px 10px;
  margin-bottom: 10px;
}

#header * {
  vertical-align: middle;
}

#header img {
  width: 70px;
}

#header span {
  color: white;
  font-size: 200%;
  margin-left: 20px;
  text-shadow: 2px 2px #212121;
}
</style>
