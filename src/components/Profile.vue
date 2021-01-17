<template>
    <div class="card">
        <div class="photo">
            <img :src="gitinfos.avatar_url" :alt="gitinfos.name" />
        </div>
        <div class="name">
            <h1>{{gitinfos.name}}</h1>
            <p>alias {{gitinfos.login}}</p>
        </div>
        <div class="job">
            <h2>Développeuse web</h2>
            <small>(25 ans et toutes ses dents <i class="em em-tooth" aria-role="presentation" aria-label="TOOTH"></i>)</small>
        </div>
    </div>
</template>

<script>
  import axios from "axios";
export default {
  name: 'Profile',
  data(){
    return{
      gitinfos: '',
    };
  },
  created: function () {
    axios.get('https://api.github.com/users/Laurie24').then(response => this.gitinfos = response.data
    )
  }
}
</script>

<style lang="scss" scoped>
    @import "../style/components/profile.scss";
</style>
