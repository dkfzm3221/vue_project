<template>
    <section>
        <ul>
            <li v-for="item in todoList" :key="item.id">
                <font-awesome-icon class="checkBtn" icon="check"/>
                {{item.id}} {{item.todo}}
                <font-awesome-icon class="removeBtn" icon="trash-alt"
                @click="removeItem(item.i_todo)"
                />
            </li>
        </ul>
    </section>
</template>
<script>
export default {
    props:['todoList'],
    methods:{
        removeItem(i_todo){
            this.$emit('removeItem', i_todo)
        }
    }
}
</script>
<style scoped>
ul{
    list-style-type: none;
    padding-left: 0px;
    margin-top: 0;
    text-align: left;
}
li{
    display: flex;
    min-height: 50px;
    height: 50px;
    line-height: 50px;
    margin: 0.5rem 0;
    padding: 0 0.9rem;
    background-color: 5px;
}
.checkBtn {
    line-height: 45px;
    color: #62acde;
    margin-right: 5px;
    margin-top: 17px;
}

.removeBtn {
    margin-left: auto;
    color: #de4343;
    margin-top: 17px;
}
</style>