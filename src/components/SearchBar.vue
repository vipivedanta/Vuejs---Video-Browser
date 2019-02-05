<template>
    <div class="col-12">
    <input type="text" @input="onInput" class="form-control" placeholder="Search videos here..." />
    </div>
</template>

<script>
    export default{
        name : 'SearchBar',
        methods : {
            onInput(e){
                this.$emit('termChange',e.target.value);
            }
        }
    }
</script>

<style></style>