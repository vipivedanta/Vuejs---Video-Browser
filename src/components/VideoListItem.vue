<template>
    <li class="list-group-item">
        <img :src="video.snippet.thumbnails.default.url" class="thumbnail" />
        {{ video.snippet.title }}
    </li>
</template>

<script>
export default {
    name : 'VideoListItem',
    props : ['video']
}
</script>

