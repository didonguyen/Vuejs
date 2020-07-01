<template>
  <div class="demo-slot">
      <comp-tabs title="This is title">
          <ul class="tabs-header">
              <li v-for="(item, index) in tabsHeader" v-bind:key="index"
                v-on:click="setActiveTab(index)" v-bind:class="{ active: tabActive == index }"
              > {{ item.text }}</li>
          </ul>
          <div class="tab-content tab1" v-if="tabActive == 0">
              <p>1. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quasi neque maxime cupiditate quaerat, laboriosam reiciendis aliquam minus placeat perferendis consequuntur provident assumenda quis ducimus molestias veritatis mollitia atque nulla alias.</p>
          </div>
          <div class="tab-content tab2" v-else-if="tabActive == 1">
              <p>2. Lorem ipsum dolor sit, amet consectetur adipisicing elit. Accusantium nulla molestias commodi modi! Minus, nemo accusantium dignissimos ipsam saepe minima dolorem odit, molestiae nesciunt laborum ducimus est iste inventore eaque.</p>
          </div>
          <div class="tab-content tab3" v-else>
              <p>3. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quasi veniam fuga inventore aut ad possimus blanditiis, tempora magni consectetur. Repellendus, et! Ullam soluta nobis reprehenderit ipsa explicabo ratione eveniet laboriosam?</p>
          </div>
      </comp-tabs>
  </div>
</template>

<script>
import CompTabs from './CompTabs.vue';
export default {
  name: 'DemoSlot',
  data() {
      return {
          tabsHeader: [
              { text: 'tab1'},
              { text: 'tab2'},
              { text: 'tab3'}
          ],
          tabActive: 0
      }
  },
  components: {
      CompTabs
  },
  methods: {
      setActiveTab(index){
          this.tabActive = index;
      }
  }
};
</script>

<style>
    .demo-slot{
        margin-top: 100px;
        padding: 100px 30px;
        border: 1px solid #000
    }
</style>
