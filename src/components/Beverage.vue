<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />
    <Contents>
      <template v-slot:top>
        <Creamer v-if="hasCreamer" :color="creamer.color" />
      </template>
      <template v-slot:mid>
        <Syrup v-if="hasSyrup" :color="syrup.color" />
      </template>
      <template v-slot:bottom>
        <Base :color="base.color" />
      </template>
    </Contents>
  </Mug>
</template>
<script setup lang="ts">
import { computed } from "vue";
import Contents from "./Contents.vue";
import Mug from "./Mug.vue";
import Syrup from "./Syrup.vue";
import Base from "./Base.vue";
import Creamer from "./Creamer.vue";
import Hot from "./Hot.vue";
import Cold from "./Cold.vue";
import type {
  BaseBeverageType,
  CreamerType,
  SyrupType,
} from "../stores/beverage";

type Props = {
  isIced: boolean;
  base: BaseBeverageType;
  creamer: CreamerType;
  syrup: SyrupType;
};
const props = defineProps<Props>();

// Layers stack in normal flow, so leaving one out closes the gap
const hasCreamer = computed(() => props.creamer.id !== "c1");
const hasSyrup = computed(() => props.syrup.id !== "s1");
</script>
