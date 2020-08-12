<template>
  <div>
    <a-collapse @change="changeActivekey">
      <a-collapse-panel key="1" header="This is panel header 1">
        <a-collapse default-active-key="4">
          <a-collapse-panel key="4" header="This is panel nest panel">
            <a-list item-layout="horizontal" :data-source="data">
    <a-list-item slot="renderItem" slot-scope="item, index">
      <a-list-item-meta description="Ant Design, a design language for background applications, is refined by Ant UED Team">
        <a-badge :count="count">
        <a href="#" class="head-example" />
      </a-badge>
      </a-list-item-meta>
      <a-button-group>
        <a-button @click="decline">
          <a-icon type="minus" />
        </a-button>
        <a-button @click="increase">
          <a-icon type="plus" />
        </a-button>
      </a-button-group>
    </a-list-item>
  </a-list>
          </a-collapse-panel>
        </a-collapse>
      </a-collapse-panel>
      <a-collapse-panel key="2" header="This is panel header 2" :disabled="false">
        <p>{{ text }}</p>
      </a-collapse-panel>
      <a-collapse-panel key="3" header="This is panel header 3">
        <p>{{ text }}</p>
      </a-collapse-panel>
    </a-collapse>
  </div>
</template>
<script>
const data = [
  {
    title: 'Ant Design Title 1',
  },
  {
    title: 'Ant Design Title 2',
  },
  {
    title: 'Ant Design Title 3',
  },
  {
    title: 'Ant Design Title 4',
  },
];
export default {
  data() {
    return {
      text: `A dog is a type of domesticated animal.Known for its loyalty and faithfulness,it can be found as a welcome guest in many households across the world.`,
      data,
      count: 5,
    };

  },
  methods: {
    changeActivekey(key) {
      console.log(key);
    },
    decline() {
      let count = this.count - 1;
      if (count < 0) {
        count = 0;
      }
      this.count = count;
    },
    increase() {
      this.count++;
    },
  },
};
</script>
