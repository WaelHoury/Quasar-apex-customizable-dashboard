<template>
  <q-page style="width: 100%; margin-top: 10px; height: 100%">
    <div class="q-pa-md">
      Edit mode
      <q-toggle v-model="editable" />
    </div>
    <GridLayout
      :layout="layout"
      :col-num="8"
      :row-height="30"
      :is-draggable="editable"
      :responsive="false"
      :is-resizable="editable"
      :is-bounded="bounded"
      :vertical-compact="true"
      :use-css-transforms="true"
      :restoreOnDrag="false"
    >
      <!-- {{ layout[3].x }} {{ layout[3].y }} {{ layout[3].w }} {{ layout[3].h }} -->
      <GridItem
        class="q-pa-sm"
        :x="layout[0].x"
        :y="layout[0].y"
        :w="layout[0].w"
        :h="layout[0].h"
        :i="layout[0].i"
        :preserveAspectRatio="true"
      >
        <LineChart></LineChart>
      </GridItem>
      <GridItem
        class="q-pa-sm"
        :x="layout[1].x"
        :y="layout[1].y"
        :w="layout[1].w"
        :h="layout[1].h"
        :i="layout[1].i"
      >
        <bar></bar>
      </GridItem>
      <GridItem
        class="q-pa-sm"
        :x="layout[2].x"
        :y="layout[2].y"
        :w="layout[2].w"
        :h="layout[2].h"
        :i="layout[2].i"
      >
        <Donut></Donut>
      </GridItem>
      <GridItem
        class="q-pa-sm"
        :x="layout[3].x"
        :y="layout[3].y"
        :w="layout[3].w"
        :h="layout[3].h"
        :i="layout[3].i"
      >
        <Radar></Radar>
      </GridItem>
      <GridItem
        class="q-pa-sm"
        :x="layout[4].x"
        :y="layout[4].y"
        :w="layout[4].w"
        :h="layout[4].h"
        :i="layout[4].i"
      >
        <Mix></Mix>
      </GridItem>
      <GridItem
        class="q-pa-sm"
        :x="layout[5].x"
        :y="layout[5].y"
        :w="layout[5].w"
        :h="layout[5].h"
        :i="layout[5].i"
      >
        <Pile></Pile>
      </GridItem>
    </GridLayout>
  </q-page>
</template>

<script setup>
import { GridLayout, GridItem } from "vue3-grid-layout-next";
import { defineAsyncComponent, defineComponent, ref } from "vue";

const components = defineComponent(GridLayout, GridItem);
const layout = ref([
  { x: 0, y: 0, w: 2, h: 7, i: "0" },
  { x: 2, y: 0, w: 2, h: 7, i: "1" },
  { x: 4, y: 0, w: 2, h: 7, i: "2" },
  { x: 6, y: 0, w: 2, h: 7, i: "3" },
  { x: 0, y: 5, w: 4, h: 13, i: "4" },
  { x: 4, y: 3, w: 4, h: 13, i: "5" },
  { x: 0, y: 5, w: 2, h: 5, i: "6" },
  { x: 2, y: 5, w: 2, h: 5, i: "7" },
  { x: 4, y: 5, w: 2, h: 5, i: "8" },
  { x: 6, y: 4, w: 2, h: 4, i: "9" },
  { x: 8, y: 4, w: 2, h: 4, i: "10" },
  { x: 10, y: 4, w: 2, h: 4, i: "11" },
  { x: 0, y: 10, w: 2, h: 5, i: "12" },
  { x: 2, y: 10, w: 2, h: 5, i: "13" },
  { x: 4, y: 8, w: 2, h: 4, i: "14" },
  { x: 6, y: 8, w: 2, h: 4, i: "15" },
  { x: 8, y: 10, w: 2, h: 5, i: "16" },
  { x: 10, y: 4, w: 2, h: 2, i: "17" },
  { x: 0, y: 9, w: 2, h: 3, i: "18" },
  { x: 2, y: 6, w: 2, h: 2, i: "19" },
]);
const editable = ref(true);
const bounded = ref(false);
const LineChart = defineAsyncComponent(() =>
  import("components/charts/LineChart.vue")
);
const bar = defineAsyncComponent(() =>
  import("components/charts/BarChart.vue")
);
const Donut = defineAsyncComponent(() =>
  import("components/charts/DonutChart.vue")
);
const Mix = defineAsyncComponent(() =>
  import("components/charts/MixChart.vue")
);
const Radar = defineAsyncComponent(() =>
  import("components/charts/RadarChart.vue")
);
const Pile = defineAsyncComponent(() =>
  import("components/charts/PileChart.vue")
);
defineOptions({
  name: "IndexPage",
});
</script>
