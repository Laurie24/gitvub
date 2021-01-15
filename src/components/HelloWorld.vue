<template>
    <div>
        <div v-for="gitinfo in gitinfos" :key="gitinfo.id">
            {{ gitinfo.name }}
        </div>
    </div>
</template>

<script>
  import axios from "axios";
export default {
  name: 'HelloWorld',
  data(){
    return{
      gitinfos: [],
    };
  },
  created: function () {
    axios.get('https://api.github.com/users/Laurie24').then(response => this.gitinfos = response.data
    )
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
