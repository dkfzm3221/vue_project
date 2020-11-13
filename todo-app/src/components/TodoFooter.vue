<template>
    <div class="clearAllContainer">
        <span class="clearAllBtn" @click="removeAll">Clear All</span>

    </div>
</template>
<script>
export default {
    methods:{
        removeAll(){
            this.$emit('removeAll')
        }
    }

    
}
</script>