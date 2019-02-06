<template>
    <div class="col-md-12">
    <div class="row">
        <div class="col-md-9">
            <input type="text" @input="clearErrorMsg" v-model="keyword" class="form-control" placeholder="Search videos here..." />
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
                this.$emit('termChange',this.keyword);
            },
            clearErrorMsg(){
                this.$emit('clearMsg');
            }
        }
    }
</script>

<style></style>