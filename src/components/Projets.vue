<template>
    <div class="dashboard">
        <h3><i class="em em-arrow_upper_right" aria-role="presentation" aria-label="NORTH EAST ARROW"></i> Mes repositories</h3>
        <div class="container">
            <div  v-for="repo in repos" :key="repo.id">
                <div class="card">
                    <h4>{{repo.name}}</h4>
                    <p>{{repo.description}}</p>
                    <p>{{repo.language}}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from "axios";
    export default {
        name: 'Projets',
        data(){
            return{
                repos: '',
            };
        },
        created: function () {
            axios.get('https://api.github.com/users/Laurie24/repos').then(response => this.repos = response.data
            )
        }
    }
</script>

<style lang="scss" scoped>
    @import "../style/components/repository.scss";
</style>
