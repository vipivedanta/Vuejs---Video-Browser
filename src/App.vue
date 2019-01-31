<template>
<div>
<div>Video Browser</div>
<SearchBar></SearchBar>
</div>
</template>

<script>
import SearchBar from './components/SearchBar';
export default{
    name : 'App',
    components : {
        SearchBar : SearchBar
    }
}
</script>