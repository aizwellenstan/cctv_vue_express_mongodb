<template>
  <div>
    <div height="500px" />
    <section :class="[isLogin ? 'app-main-active': 'app-main']">
      <transition name="fade-transform" mode="out-in">
        <!-- <keep-alive :include="cachedViews"> -->
        <router-view :key="key" style="padding-top: 4%;padding-bottom: 2.5%" />
        <!-- </keep-alive> -->
      </transition>
    </section>
  </div>
</template>

<script>
export default {
  name: 'AppMain',
  data() {
    return {
      isLogin: localStorage.getItem('token') === 'ImLogin'
    }
  },
  computed: {
    cachedViews() {
      return this.$store.state.tagsView.cachedViews
    },
    key() {
      return this.$route.path
    }
  }
}
</script>

<style lang="scss" scoped>
.active {
  margin-left:210px;
}

.app-main {
  /* 50= navbar  50  */
  min-height: calc(100vh - 50px);
  width: 100%;
  position: relative;
  overflow: hidden;
}

.app-main-active {
  min-height: calc(100vh - 108px);
  margin-left:210px;
  width: calc(100% - 210px);
  position: relative;
  overflow: hidden;
}

.fixed-header+.app-main {
  padding-top: 50px;
}

.hasTagsView {
  .app-main {
    /* 84 = navbar + tags-view = 50 + 34 */
    min-height: calc(100vh - 84px);
  }

  .fixed-header+.app-main {
    padding-top: 84px;
  }
}
</style>

<style lang="scss">
// fix css style bug in open el-dialog
.el-popup-parent--hidden {
  .fixed-header {
    padding-right: 15px;
  }
}
</style>
