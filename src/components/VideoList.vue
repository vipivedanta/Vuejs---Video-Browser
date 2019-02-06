<template>
   <div>
        <ul class="list-group">
        <VideoListItem 
                v-for="video in videos" 
                :video="video"
                @videoSelect="VideoSelect"
        ></VideoListItem>
        </ul>
   </div>
</template>

<script>

import VideoListItem from './VideoListItem';

export default {
    name : 'VideoList',
    props : ['videos'],
    components : {
        VideoListItem : VideoListItem
    },
    methods : {
        VideoSelect(video){
            this.$emit('onVideoSelect',video);
        }
    }
}
</script>

<style>

</style>

