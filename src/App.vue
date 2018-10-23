<template>
  <div id="app">
    <div class="navbar">
      <div class="left">Team-UI</div>
      <div class="right">
        <div>Guide</div>
        <div>API Reference</div>
        <div>Release Notes</div>
        <div>Languages</div>
        <div>GitHub</div>
      </div>
    </div>
    <div class="down">
      <div class="left">
        <ul class="slideBar">
          <li v-for="(item, index) in sidebar" :key="index">
            <p v-if="item.type === 'head'" class="sidebar-heading">{{item.name}}</p>
            <a @click="sidebarclick = index" :class="{'active': sidebarclick === index}" v-else class="slide-link" :href="item.url">{{item.name}}</a>
          </li>
        </ul>
      </div>
      <div class="body">
        <router-view></router-view>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      sidebarclick: '',
      sidebar: [
        {
          type: 'head',
          name: 'base'
        },
        {
          type: 'link',
          name: 'waht is team-ui',
          url: '/#/base/home'
        },
        {
          type: 'link',
          name: 'waht is team-ui',
          url: '/#/base/home'
        },
        {
          type: 'link',
          name: 'waht is team-ui',
          url: '/#/base/home'
        },
        {
          type: 'link',
          name: 'waht is team-ui',
          url: '/#/base/home'
        }
      ]
    }
  },
}
</script>

<style lang="scss" scoped>
#app{
  display: flex;
  flex-flow: column;
  height: 100%;
  >.navbar{
    padding: .7rem 1.5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #fff;
    box-sizing: border-box;
    border-bottom: 1px solid #eaecef;
    >.left{
      font-size: 1.3rem;
      font-weight: 600;
      color: #2c3e50;
      position: relative;
    }
    >.right{
      display: flex;
      >div{
        cursor: pointer;
        position: relative;
        display: inline-block;
        margin-left: 1.5rem;
        line-height: 2rem;
        font-size: .9rem;
      }
    }
  }
  >.down {
    flex: 1;
    display: flex;
    >.left{
      font-size: 15px;
      width: 16.4rem;
      border-right: 1px solid #eaecef;
      overflow: auto;
      >.slideBar{
        padding: 1.5rem 0;
        .sidebar-heading{
          color: #999;
          transition: color .15s ease;
          font-size: 1.1em;
          font-weight: 700;
          padding-left: 1.5rem;
          margin-top: 0;
          margin-bottom: .5rem;
        }
        .slide-link{
          font-weight: 400;
          display: inline-block;
          color: #2c3e50;
          border-left: .25rem solid transparent;
          padding: .35rem 1rem .35rem 1.25rem;
          line-height: 1.4;
          width: 100%;
          box-sizing: border-box;
        }
        .active {
          font-weight: 600;
          color: #3eaf7c;
          border-left-color: #3eaf7c;
        }
      }
    }
    >.body{
      flex: 1;
    }
  }
}
</style>
