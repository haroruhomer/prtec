<template>
  <div id="app">
    <aside id="nav">
      <h1>System</h1>
      <ul>
        <li><img class="link-icon" src="./assets/users.png" alt="users-link"><router-link to="/">Users</router-link></li>
      </ul>
    </aside>
    <article id="content">
      <div id="header-nav">
        <div id="menu">
          <div class="hamburger">
            <div></div>
            <div></div>
            <div></div>
          </div>
          
          <div>Dashboard</div>
        </div>
        <div id="user" class="profile-info">
          <img class="avatar" src="https://via.placeholder.com/150" alt="Harold Molina">
          <span class="name">Harold Molina</span>
        </div>
      </div>
      <div class="views">
        <router-view/>
      </div>
    </article>
  </div>
</template>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css?family=Roboto:400,500&display=swap');
$bgCard : #ffffff;
#app {
  display:flex;
  background: #f5f6fa;
  height: 100vh;
  font-family: Roboto;
}

#nav {
  padding: 30px;
  height: 100%;
  width:20%;
  background: $bgCard;
  ul{
    list-style: none;
    text-decoration: none;
    .router-link-active{
      text-decoration: none;
      color: black;
    }
    .link-icon{
      margin-right: 15px;
    }
  }
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
  #menu{
    margin: 0 35px;
    display: flex;
    .hamburger {
      margin-right: 5px;
      width: 15px;
      & div{
        margin: 2px 0;
        width: 100%;
        height: 1px;
        border: 1px solid gray;
        background: gray;
        border-radius: 5px;
        &:last-child{
          margin-left: 50%;
          width: 50%;
        }
    }

    }
  }
  .profile-info{
    margin: 0 35px;
    display: flex;
    align-items: center;
    .avatar{
      height: 32px;
      width: 32px;
      border-radius: 50%;
      margin-right: 15px;
    }
  }
}
</style>
