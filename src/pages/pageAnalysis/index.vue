<template>
  <div class="container">
    <el-cascader
      v-model="state.cascaderData"
      :options="options"
      :show-all-levels="false"
      :props="{
        checkStrictly: true,
      }"
    />
  </div>
</template>
<script setup lang="ts">
import { reactive } from "vue";
interface State {
  cascaderData: string[];
}
const state: State = reactive({
  cascaderData: [],
});
const options = [
  {
    value: "guide",
    label: "Guide",
    disabled: true,
    children: [
      {
        disabled: true,
        value: "disciplines",
        label: "Disciplines",
        children: [
          {
            value: "consistency",
            label: "Consistency",
          },
          {
            value: "feedback",
            label: "Feedback",
          },
          {
            value: "efficiency",
            label: "Efficiency",
          },
          {
            value: "controllability",
            label: "Controllability",
          },
        ],
      },
      {
        value: "navigation",
        label: "Navigation",
        disabled: true,
        children: [
          {
            value: "side nav",
            label: "Side Navigation",
          },
          {
            value: "top nav",
            label: "Top Navigation",
          },
        ],
      },
    ],
  },
];
</script>
<style scoped lang="scss"></style>
