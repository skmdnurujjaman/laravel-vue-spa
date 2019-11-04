<template>
    <div class="container">
         <profile></profile>
         <userList></userList>
    </div>
</template>
<script>
  import profile from '../../components/profile.vue'
  import userList from '../../components/user-list.vue'
  export default {
    mounted() {
      //
    },
    components: {
      profile,
      userList
    }
  }
</script>