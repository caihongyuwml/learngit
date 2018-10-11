<template>
  <div class="sidebar">
    <transition name="fade" @touchmove.stop.prevent>
      <div class="menu-mask" v-show="isReallShow" @click="hideMenu"></div>
    </transition>

    <transition name="side">
      <div class="menu-content" v-show="isReallShow">
        <div class="menu-detail">
          <div class="menu-userInfo">
            <img class="avatat " width="56" height="56">
            <div class="user-detail">
              <span class="name">梦林</span>
              <img class="isvip" src="../assets/vip.png" alt="">
              <span class="progress">Lv.3</span>
            </div>
          </div>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
  const SHOW_SIDEBAR = true
  const HIDE_SIDEBAR = false

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
      data(){
        return{

        }
      },
      methods:{
        hideMenu(){
          return sideBar.actions.hideSideBar
        }
      },
      computed:{
        isReallShow(){
          return sideBar.state.isShow
        }
      }
    }
</script>

<style scoped>
.menu-mask {
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.5);
}
</style>
