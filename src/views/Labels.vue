<template>
  <Layout>
    <div class="tags">
      <router-link :key="tag.id"
                   :to="`/labels/edit/${tag.id}`"
                   class="tag"
                   v-for="tag in tags">
        <span>{{tag.name}}</span>
        <Icon name="right"/>
      </router-link>
    </div>
    <div class="createTag-wrapper">
      <Button @click="newTag" class="createTag">新建状态</Button>
    </div>
  </Layout>
</template>

<script lang="ts">
  import {Component} from "vue-property-decorator";
  import Button from "@/components/Button.vue";
  import {mixins} from "vue-class-component";
  import TagHelper from "@/mixins/TagHelper";

  @Component({
    components: {Button}
  })
  export default class Labels extends mixins(TagHelper) {
    get tags() {
      return this.$store.state.tagList;
    }

  }
</script>

<style lang="scss" scoped>
  .tags {
    background: white;
    font-size: 16px;
    padding-left: 16px;

    .tag {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 10px 30px;
      border-bottom: 1px solid #e6e6e6;
      min-height: 44px;
    }

    svg {
      width: 18px;
      height: 18px;
      color: #666;
      margin-right: 16px;
    }
  }

  .createTag-wrapper {
    text-align: center;
    padding: 16px;
    margin-top: 44-16px;

    > .createTag {
      /*background: darken(#f6c646, 8%);*/
      background: #009bff;
    }
  }
</style>
