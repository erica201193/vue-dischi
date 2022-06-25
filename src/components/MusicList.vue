<template>
    <div class="bg-darkgray">
        <div class="container">
            <div>
                <Search></Search>
            </div>
            <div class="row row-cols-5 py-5">
            <div class="col pt-5 pb-2 d-flex" v-for="(music, i) in musicList" :key="i">
                <div class="my-card card p-3 text-white text-center shadow">
                    <img :src="music.poster" alt="">
                    <h4 class="text-uppercase fw-bold py-4">{{music.title}}</h4>
                    <div>{{ music.author }}</div>                    
                    <div>{{ music.year }}</div>

                </div>
            </div>
        </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";
import Search from "./Search.vue"
export default {
    name: "MusicList",
    components: { Search },
    data() {
        return {
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            musicList: []

        }
    },
    methods: {
        fetchMusicList() {
            axios.get(this.apiUrl).then((resp) => {
                this.musicList.push(...resp.data.response)
                
            });
        },
    },
    mounted() {
        this.fetchMusicList()
    }
};
</script>

<style lang="scss" scoped>
.bg-darkgray {
    background-color: #1E2D3B;
}
.bg-gray {
    background-color: #2D3A46;
}

.my-card {
    background-color: #2D3A46;
    div {
        color: gray;
    }

}

</style>