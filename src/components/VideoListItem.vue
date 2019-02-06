<template>
    <li class="list-group-item" @click="onVideoSelect">
        <img :src="thumbnailUrl" class="thumbnail" />
        {{ video.snippet.title }}
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

