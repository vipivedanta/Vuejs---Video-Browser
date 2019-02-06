<template>
<div>

<div v-if="noItemEntered == true" class="col-md-12 alert alert-danger">
        <p>You haven't typed a word to search..</p>    
</div> 

<div v-if="video" class="col-md-12">
    <div class="row">
        <div class="embed-responsive embed-responsive-16by9">
            <iframe :src="videoUrl" class="embed-responsive-item" ></iframe>
        </div>
        <div class="video-details col-md-12">
            <h5>{{ video.snippet.title }}</h5>
            <p>{{ video.snippet.description }}</p>
        </div>
    </div>
</div>

</div>
</template>

<script>
export default {
    name : 'VideoDetail',
    props : ['video','noItemEntered'],
    computed : {
        videoUrl(){
            const videoId = this.video.id.videoId;
            return 'https://youtube.com/embed/' + videoId + '?showinfo=0&controls=0';
        }
    }
}
</script>

<style>
.video-player{
    height:500px;
}
</style>
