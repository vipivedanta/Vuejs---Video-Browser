<template>
    <li class="list-group-item" @click="onVideoSelect">
        <div class="col-md-12">
        <div class="row">
            <div class="col-md-5">
             <img :src="thumbnailUrl" class="thumbnail" />
            </div>
            <div class="col-md-7">
            {{ video.snippet.title }}
            </div>
        </div>
        </div>
    </li>
</template>

<script>
export default {
    name : 'VideoListItem',
    props : ['video'],
    computed : {
        thumbnailUrl(){
            return this.video.snippet.thumbnails.default.url;
        }
    },
    methods : {
        onVideoSelect(){
            this.$emit('videoSelect',this.video);
        }
    }
}
</script>

