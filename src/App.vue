<template>
<div>
    <h3>Video Browser</h3>
    <div class="row">
        
    </div>
    <div class="row">
        <div class="col-6"><SearchBar @termChange="onTermChange"></SearchBar></div>
        <div class="col-6"><VideoList :videos="videos"></VideoList></div>
    </div>
</div>
</template>

<script>
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
import axios from 'axios';

const YOUTUBE_DATA_API_KEY = 'AIzaSyCspE3SO1up8-jBCj5dbKHzxfRgM3tR-JA';

export default{
    name : 'App',
    components : {
        SearchBar : SearchBar,
        VideoList : VideoList
    },
    data(){
        return {
            videos : []
        }
    },
    methods : {
        onTermChange(searchTerm){
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
        }
    }
}
</script>