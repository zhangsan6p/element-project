<template>
  <el-tabs v-model="editableTabsValue" type="card" closable @tab-remove="removeTab">
    <el-tab-pane
        v-for="item in editableTabs"
        :key="item.name"
        :label="item.title"
        :name="item.name"
    >
      {{item.content}}
    </el-tab-pane>
  </el-tabs>
</template>

<script>
import {mapState} from "vuex";
export default {
  name: "tabs.vue",
  data() {
    return {
    }
  },
  computed:{
    ...mapState(
        {
          editableTabsValue:
              state => state.MenuStore.editableTabsValue,
          editableTabs:
              state => state.MenuStore.editableTabs
        }
    )
  },
  methods: {
    removeTab(targetName) {
      let Tabs = this.editableTabs;
      let activeName = this.editableTabsValue;
      if (activeName === targetName) {
        Tabs.forEach((tab, index) => {
          if (tab.name === targetName) {
            let nextTab = Tabs[index + 1] || Tabs[index - 1];
            if (nextTab) {
              activeName = nextTab.name;
            }
          }
        });
      }
      this.editableTabsValue = activeName;
      this.editableTabs = Tabs.filter(tab => tab.name !== targetName);
    }
  }
}
</script>

<style scoped>

</style>
