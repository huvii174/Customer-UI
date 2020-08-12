<template>
  <div class="block">
    <el-timeline>
      <el-timeline-item v-for="(item,index) of timeline" :key="index" :items="item.items" placement="top">
        <el-card>
          <h1>{{ item.items }}</h1>
          <p>Price : {{ item.price }} $</p>
          <p>Quality : {{ item.quality }} </p>
        </el-card>
      </el-timeline-item>
    </el-timeline>
    <h2> Total : </h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      timeline: [
        {
          items: 'Cake',
          price: 30,
          quality: 2
        },
        {
          items: 'Cake',
          price: 30,
          quality: 2
        },
        {
          items: 'Cake',
          price: 30,
          quality: 2
        }
      ]
    }
  }

//   computed : {
//       getTotal() {
//           for (items) {
              
//           }
//       }
//   }
}
</script>
