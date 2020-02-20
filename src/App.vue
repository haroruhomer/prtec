<template>
  <div id="app">
    <aside id="nav">
      <h1>System</h1>
      <ul>
        <li><router-link to="/">Users</router-link></li>
      </ul>
    </aside>
    <article id="content">
      <div id="header-nav">
        <div id="menu">
          Dashboard
        </div>
        <div id="user" class="">
          Harold Molina
        </div>
      </div>
      <div class="views">
        <router-view/>
      </div>
    </article>
  </div>
</template>

<style lang="scss">
$bgCard : #ffffff;
#app {
  display:flex;
  background: #f5f6fa;
  height: 100vh;
}

#nav {
  padding: 30px;
  height: 100%;
  width:20%;
  background: $bgCard;
}
#content{
  width : 80%;
  padding: 0 36px;
}
#header-nav{
  background: #ffffff;
  width: 100%;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  justify-content: space-between;
  min-height: 74px;
  align-items: center;
  & div {
    margin: 0 35px;
  }
}
</style>
