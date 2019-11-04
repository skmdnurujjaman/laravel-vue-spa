<template>
    <div id="main">
        <header id="header">
            <h3><b-badge variant="light">
                <router-link :to="{name: 'home'}">
                    Laravel Vue SPA
                </router-link>
                </b-badge>
            </h3>
            <navigationMenu></navigationMenu>
        </header>
        <div id="content">
            <router-view></router-view>
        </div>
    </div>
</template>
<script>
  import navigationMenu from './components/Menu.vue'
  export default {
    data() {
      return {
        //
      }
    },
    components: {
      navigationMenu
    }
  }
</script>