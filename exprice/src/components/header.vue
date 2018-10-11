<template>
  <div class="header">
    <div class="header-warpper">
      <i class="menu icon-menu" @click ="showMuen"></i>
      <div class="center-menu" @click="hideMenu">
        <i class="music icon-music"></i>
        <i class="music icon-wangyi"></i>
        <i class="music icon-community"></i>
      </div>
      <i class="search icon-search"></i>
    </div>
  </div>
</template>

<script>
  // const SHOW_SIDEBAR = true
  // const HIDE_SIDEBAR = false
  //
  const sideBar = {
    state: {
      isShow: false
    },
    mutations: {
      showBar(state) {
        state.isShow = SHOW_SIDEBAR
      },
      hideBar(state) {
        state.isShow = HIDE_SIDEBAR
      }
    },
    actions: {
      showSideBar({commit}) {
        commit('showBar')
      },
      hideSideBar({commit}) {
        commit('hideBar')
      }
    },
    getters: {
      isShowMethod() {
        return this.state.isShow
      }
    }
  }
    export default {
      props:{
        showMenu:{
          type:Boolean,
          default:false
        }
      },
      data(){
        return{
          isShowMenu:this.showMenu
        }
      },
      methods:{
        showMuen(){
          return sideBar.actions.showSideBar
        },
        hideMenu(){
          return sideBar.actions.hideSideBar
        }
      }
    }
</script>

<style scoped>
  .header{
    background: #C62F2F;
    position: fixed;
    top:0;
    right:0;
    left:0;
    height:50px;
  }
  .header-warpper{
    display:flex;
    justify-content: space-between;
    align-items: center;
  }
  .icon-menu,.icon-search{
    color:#fff;
    font-size:26px;
    padding:10px 15px;
  }
  .center-menu{
    font-size:24px;
  }
  i{
    margin:0 5px;
    color: #eeeeee;
  }
  i:active{
    color:#ccafaf;
  }
</style>
