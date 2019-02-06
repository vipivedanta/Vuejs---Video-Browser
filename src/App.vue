<template>
<div class="">
    
    <div class="mt-20">
        <div class="col-md-6"><SearchBar @clearMsg="clearMsg" @termChange="onTermChange"></SearchBar></div> 
    </div>

    <div class="mt-20">
        <div class="col-md-12">
            <div class="row">
                <div class="col-md-8"><VideoDetail :noItemEntered="noItemEntered" :video="selectedVideo"></VideoDetail></div>
                <div class="col-md-4"><VideoList :videos="videos" @onVideoSelect="videoSelect"></VideoList></div>
            </div>
        </div>
    </div>

</div>
</template>

<script>
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
import VideoDetail from './components/VideoDetail';
import axios from 'axios';

const YOUTUBE_DATA_API_KEY = 'AIzaSyCspE3SO1up8-jBCj5dbKHzxfRgM3tR-JA';

export default{
    name : 'App',
    components : {
        SearchBar : SearchBar,
        VideoList : VideoList,
        VideoDetail : VideoDetail
    },
    data(){
        return {
            videos : [],
            selectedVideo : '',
            noItemEntered : false
        }
    },
    methods : {
        onTermChange(searchTerm){
            if(searchTerm == ''){
                this.noItemEntered = true;
                return;
            }

            this.noItemEntered = false;
            axios.get('https://www.googleapis.com/youtube/v3/search',{
                params : {
                    key : YOUTUBE_DATA_API_KEY,
                    type : 'video',
                    part : 'snippet',
                    q : searchTerm
                }
            }).then(response => {
                this.videos = response.data.items;
            });
        },
        videoSelect(video){
            this.selectedVideo = video;
        },
        clearMsg(){
            this.noItemEntered = false;

        }
    }
}
</script>

<style>
.mt-20{
    margin-top:20px;
}
</style>
