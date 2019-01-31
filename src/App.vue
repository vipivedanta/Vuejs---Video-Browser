<template>
<div>
<div>Video Browser</div>
<SearchBar @termChange="onTermChange"></SearchBar>
</div>
</template>

<script>
import SearchBar from './components/SearchBar';
const YOUTUBE_DATA_API_KEY = 'AIzaSyCspE3SO1up8-jBCj5dbKHzxfRgM3tR-JA';

export default{
    name : 'App',
    components : {
        SearchBar : SearchBar
    },
    methods : {
        onTermChange(searchTerm){
            console.log(searchTerm);
        }
    }
}
</script>