<template>
  <div id="app">
    <button
      v-for="(tab, index) in tabs"
      :key="index"
      :class="['tab-button', { active: currentTab === tab }]"
      @click="currentTab = tab"
    >
      {{ currentButtonContent }}
    </button>

    <keep-alive>
      <component :is="currentTab" class="tab"></component>
    </keep-alive>
  </div>
</template>

<script>
import TabPosts from './components/TabPosts.vue'
import TabArchive from './components/TabArchive.vue'

export default {
  name: 'App',
  components: {
    TabPosts,
    TabArchive
  },
  data() {
    return {
      currentTab: TabPosts,
      tabs: [TabPosts, TabArchive]
    }
  },
  computed: {
    currentButtonContent() {
      return this.currentTab == TabPosts ? 'Posts' : 'Archive'
    }
  }
}
</script>

<style>
.tab-button {
  padding: 6px 10px;
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
  border: 1px solid #ccc;
  cursor: pointer;
  background: #f0f0f0;
  margin-bottom: -1px;
  margin-right: -1px;
}
.tab-button:hover {
  background: #e0e0e0;
}
.tab-button.active {
  background: #e0e0e0;
}
.tab {
  border: 1px solid #ccc;
  padding: 10px;
}
.posts-tab {
  display: flex;
}
.posts-sidebar {
  max-width: 40vw;
  margin: 0;
  padding: 0 10px 0 0;
  list-style-type: none;
  border-right: 1px solid #ccc;
}
.posts-sidebar li {
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow: hidden;
  cursor: pointer;
}
.posts-sidebar li:hover {
  background: #eee;
}
.posts-sidebar li.selected {
  background: lightblue;
}
.selected-post-container {
  padding-left: 10px;
}
.selected-post > :first-child {
  margin-top: 0;
  padding-top: 0;
}
</style>
