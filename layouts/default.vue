<template>
  <div class="layout">
    <SideBar></SideBar>
    <div class="page-wrap">
      <Header></Header>
      <Breadcramb></Breadcramb>

      <div class="context">
        <nuxt/>
      </div>
    </div>
  </div>
</template>

<script>
import Breadcramb from "@/layouts/Breadcramb";
import SideBar from "@/layouts/SideBar";
import Header from "@/layouts/Header";

export default {
  name: 'layout',

  components: {
    Breadcramb,
    SideBar,
    Header
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Source+Sans+Pro:300,400,600,700&display=swap&subset=cyrillic');

html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

.layout {
  display: flex;
  height: 100vh;
}

.page-wrap {
  width: 100%;
}

.v-select {
  background: #fff;
  border-radius: 4px;
}

.context {
  padding: 10px 40px 20px;
}

body {
  font-family: 'Source Sans Pro', sans-serif;
}

*, *:before, *:after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>

