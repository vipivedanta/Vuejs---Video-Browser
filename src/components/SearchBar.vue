<template>
    <div class="col-md-12">
    <div class="row">
        <div class="col-md-9">
            <input type="text" v-model="keyword" class="form-control" placeholder="Search videos here..." />
        </div>
        <div class="col-md-2">
            <input type="button" value="Search" class="btn btn-info" @click="searchNow"/>
        </div>
    </div>
    </div>   
</template>

<script>
    export default{
        name : 'SearchBar',
        data(){
            return {
                keyword : ''
            }
        },
        methods : {
            onInput(e){
                this.$emit('termChange',e.target.value);
            },
            searchNow(){
                if(this.keyword == ''){
                    alert('Please type a keyword to search');
                    return;
                }
                this.$emit('termChange',this.keyword);
            }
        }
    }
</script>

<style></style>