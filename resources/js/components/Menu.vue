<template>
<div class="mb-3">
  <b-nav id="nav" tabs align="right">
    <b-nav-item v-if="!$auth.check()" v-for="(route, key) in routes.unlogged" v-bind:key="route.path" right>
        <router-link  :to="{ name : route.path }" :key="key">
                    {{route.name}}
                </router-link>
    </b-nav-item>
    <b-nav-item v-if="$auth.check(1)" v-for="(route, key) in routes.user" v-bind:key="route.path" right>
        <router-link  :to="{ name : route.path }" :key="key">
                    {{route.name}}
                </router-link>
    </b-nav-item>
    <b-nav-item v-if="$auth.check(2)" v-for="(route, key) in routes.admin" v-bind:key="route.path" right>
      <router-link  :to="{ name : route.path }" :key="key">
                    {{route.name}}
                </router-link>
    </b-nav-item>
    <b-nav-item v-if="$auth.check()" right>
      <a href="#" @click.prevent="$auth.logout()">Logout</a>
    </b-nav-item>
  </b-nav>
</div>
</template>
<script>
  export default {
    data() {
      return {
        routes: {
          // UNLOGGED
          unlogged: [
            {
              name: 'Register',
              path: 'register'
            },
            {
              name: 'Login',
              path: 'login'
            }
          ],
          // LOGGED USER
          user: [
            {
              name: 'Dashboard',
              path: 'dashboard'
            }
          ],
          // LOGGED ADMIN
          admin: [
            {
              name: 'Dashboard',
              path: 'admin.dashboard'
            }
          ]
        }
      }
    },
    mounted() {
      //
    }
  }
</script>