<template>
    <nav class="nav">
        <router-link active-class="selected" class="item" to="/labels">
            <Icon name="edit"/>
            状态编辑
        </router-link>
        <router-link active-class="selected" class="item" to="/money">
            <Icon name="weight"/>
            体重记录
        </router-link>
        <router-link active-class="selected" class="item" to="/statistics">
            <Icon name="change"/>
            数据跟踪
        </router-link>
    </nav>
</template>

<script lang="ts">

    export default {
        name: "Nav"
    };
</script>

<style lang="scss" scoped>
    .nav {
        display: flex;
        flex-direction: row;
        box-shadow: 0 0 3px rgba(0, 0, 0, 0.24);
        font-size: 12px;

        > .item {
            width: 33.33333%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 2px 0;

            .icon {
                width: 32px;
                height: 32px;
            }
        }

        > .item.selected {
            color: #009bff;
            /*color: #f6c646;*/
        }
    }

</style>