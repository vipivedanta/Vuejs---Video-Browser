<template>
   <div>
        <h3>Video List here</h3> 
        <ul class="list-group">
        <VideoListItem v-for="video in videos" :video="video"></VideoListItem>
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
    }
}
</script>

<style>

</style>

