<template>
    <div class="dashboard">
        <div class="row">
            <div class="item bio">
                <h3><i class="em em-page_with_curl" aria-role="presentation" aria-label="PAGE WITH CURL"></i> Bio</h3>
                <p>{{repos.bio}}</p>
            </div>
            <div class="item repos">
                <h3><i class="em em-arrow_upper_right" aria-role="presentation" aria-label="NORTH EAST ARROW"></i> Repositories publics</h3>
                <div class="number">
                    <p>{{repos.public_repos}}</p>
                </div>

            </div>
        </div>
        <div class="row">
            <div class="item abonne">
                <h3><i class="em em-handshake" aria-role="presentation" aria-label="HANDSHAKE"></i> Abonnement</h3>
                <p>{{repos.followers}} <br> Followers</p>
                <p>{{repos.following}} <br> Following</p>
            </div>
            <div class="item contact">
                <h3> Contact</h3>
                <p><i class="em em-round_pushpin" aria-role="presentation" aria-label="ROUND PUSHPIN"></i> {{repos.location}}</p>
                <p><i class="em em-email" aria-role="presentation" aria-label="ENVELOPE"></i> villeneuvelaurie@orange.fr</p>
                <p><i class="em em-iphone" aria-role="presentation" aria-label="MOBILE PHONE"></i> 06 78 44 86 78</p>
                <p><i class="em em-earth_africa" aria-role="presentation" aria-label="EARTH GLOBE EUROPE-AFRICA"></i> <a :href="repos.blog">{{repos.blog}}</a></p>
                <p><i class="fab fa-twitter"></i> @{{repos.twitter_username}}</p>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from "axios";
    export default {
        name: 'Info',
        data(){
            return{
                repos: '',
            };
        },
        created: function () {
            axios.get('https://api.github.com/users/Laurie24').then(response => this.repos = response.data
            )
        }
    }
</script>

<style lang="scss" scoped>
    @import "../style/components/info.scss";
</style>
