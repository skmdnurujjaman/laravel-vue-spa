<template>
  <div class="mt-3">
        <div class="alert alert-danger" v-if="has_error">
          <p>Something goes wrong</p>
        </div>
        <div v-for="u in user">
        <h1 v-if="u.name">Welcome, {{ u.name }}</h1>
        <p>{{ u.email }}</p>
        </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        has_error: false,
        user:{
          id:null,
          name:null
        }
      }
    },
    mounted() {
      this.getUsers()
    },
    methods: {
      getUsers() {
        this.$http({
          url: `auth/user`,
          method: 'GET'
        })
            .then((res) => {
              //console.log(res.data) 
              this.user = res.data
            }, () => {
              this.has_error = true
            })
      }
    }
  }
</script>