<template>
  <div id="header">
    <header id="top-header">
      <div class="flex">
        <h1 class="header-logo">estra inc.</h1>
        <nav class="header-nav">
          <ul>
            <li><a href="#">home</a></li>
            <li><a href="#">about</a></li>
            <li><a href="#">service</a></li>
            <li><a href="#">works</a></li>
            <li><a href="#">price</a></li>
            <li><a href="#">contact</a></li>
          </ul>
      </nav>
      </div>
    </header>
    <div id="hamburger" @click="hamburger()" :class="{active:isClass}">
      <span></span>
      <span></span>
      <span></span>
    </div>
    <nav class="menu-content" :class="{open:isClass}">
      <p class="menu-title">estra inc.</p>
      <ul class="menu-content_inner">
        <li>
          <a href="#">home</a>
        </li>
        <li>
          <a href="#">about</a>
        </li>
        <li>
          <a href="#">service</a>
        </li>
        <li>
          <a href="#">works</a>
        </li>
        <li>
          <a href="#">price</a>
        </li>
        <li>
          <a href="#">contact</a>
        </li>
      </ul>
    </nav>
  </div>
</template>
<script>
export default {
  data(){
    return{
      isClass:false
    }
  },
  methods:{
    hamburger(){
      this.isClass=!this.isClass
    }
  }
}
</script>
<style scoped>
#hamburger {
  display: none;
}

#top-header {
  height: 70px;
  line-height: 70px;
  background: rgba(0, 0, 0, 1);
}

.header-logo {
  font-size: 20px;
  font-weight: bold;
  margin-left: 35px;
  color: #fff;
  line-height: 70px;
}

.header-nav li {
  display: inline-block;
  margin-right: 35px;
  font-size: 16px;
}

.header-nav a {
  color: #fff;
}
.menu-content{
  position: fixed;
  top: 0px;
  left: -1500px;
  width: 100%;
  height: 100%;
  z-index: 200;
  background-color: black;
  color: white;
  text-align: center;
  padding: 10% 0;
  font-size: 20px;
  transition: 1s;
}
.menu-title, .menu-content li{margin-top: 30px;}
.menu-content a{
  color: white;
}
@media screen and (max-width:768px){
  .header-nav {
    display: none;
  }
  .top-footer .header-logo {
    margin: 0;
    width: 100%;
    text-align: center;
  }
  #hamburger {
    width: 40px;
    height: 40px;
    position: absolute;
    cursor: pointer;
    z-index: 500;
    top: 15px;
    right: 20px;
    transition: 0.4s;
    display: block;
  }
  #hamburger span {
    display: block;
    width: 35px;
    height: 2px;
    background-color: #fff;
    transition: 0.8s;
  }
  #hamburger span:nth-of-type(1) {
    position: absolute;
    top: 10px;
    left: 2px;
  }
  #hamburger span:nth-of-type(2) {
    position: absolute;
    top: 20px;
    left: 2px;
  }
  #hamburger span:nth-of-type(3) {
    position: absolute;
    top: 30px;
    left: 2px;
  }
  #hamburger.active span:nth-of-type(1){
    transform: rotate(-50deg) translate(-12px,0px);
    
  }
  #hamburger.active span:nth-of-type(2){
    display: none;
  }
  #hamburger.active span:nth-of-type(3){
    transform: rotate(50deg)translate(-13px,0px);
  }
  .menu-content.open{
    left: 0px;
    transition: 1s;
  }
}

</style>