<template>
  <div class="parent">
    <evolveConstraint
      v-for="digimon in gen1"
      :key="digimon.id"
      :name="digimon.name"
      :generation="digimon.generation"
      :hp="digimon.hp"
      :mp="digimon.mp"
      :strength="digimon.strength"
      :stamina="digimon.stamina"
      :wisdom="digimon.wisdom"
      :speed="digimon.speed"
      :weight="digimon.weight"
      :mistakes="digimon.mistakes"
      :bond="digimon.bond"
      :discipline="digimon.discipline"
      :wins="digimon.wins"
      :keyDigimon="digimon.keyDigimon"
      :keyPoints="digimon.keyPoints"
      :topPosition="digimon.topPosition"
      :leftPosition="digimon.leftPosition"
    />
    <evolveConstraint
      v-for="digimon in gen2"
      :key="digimon.id"
      :name="digimon.name"
      :generation="digimon.generation"
      :hp="digimon.hp"
      :mp="digimon.mp"
      :strength="digimon.strength"
      :stamina="digimon.stamina"
      :wisdom="digimon.wisdom"
      :speed="digimon.speed"
      :weight="digimon.weight"
      :mistakes="digimon.mistakes"
      :bond="digimon.bond"
      :discipline="digimon.discipline"
      :wins="digimon.wins"
      :keyDigimon="digimon.keyDigimon"
      :keyPoints="digimon.keyPoints"
      :topPosition="digimon.topPosition"
      :leftPosition="digimon.leftPosition"
    />
    <evolveConstraint
      v-for="digimon in gen3"
      :key="digimon.id"
      :name="digimon.name"
      :generation="digimon.generation"
      :hp="digimon.hp"
      :mp="digimon.mp"
      :strength="digimon.strength"
      :stamina="digimon.stamina"
      :wisdom="digimon.wisdom"
      :speed="digimon.speed"
      :weight="digimon.weight"
      :mistakes="digimon.mistakes"
      :bond="digimon.bond"
      :discipline="digimon.discipline"
      :wins="digimon.wins"
      :keyDigimon="digimon.keyDigimon"
      :keyPoints="digimon.keyPoints"
      :topPosition="digimon.topPosition"
      :leftPosition="digimon.leftPosition"
    />
    <evolveConstraint
      v-for="digimon in gen4"
      :key="digimon.id"
      :name="digimon.name"
      :generation="digimon.generation"
      :hp="digimon.hp"
      :mp="digimon.mp"
      :strength="digimon.strength"
      :stamina="digimon.stamina"
      :wisdom="digimon.wisdom"
      :speed="digimon.speed"
      :weight="digimon.weight"
      :mistakes="digimon.mistakes"
      :bond="digimon.bond"
      :discipline="digimon.discipline"
      :wins="digimon.wins"
      :keyDigimon="digimon.keyDigimon"
      :keyPoints="digimon.keyPoints"
      :topPosition="digimon.topPosition"
      :leftPosition="digimon.leftPosition"
    />
    <evolveConstraint
      v-for="digimon in gen5"
      :key="digimon.id"
      :name="digimon.name"
      :generation="digimon.generation"
      :hp="digimon.hp"
      :mp="digimon.mp"
      :strength="digimon.strength"
      :stamina="digimon.stamina"
      :wisdom="digimon.wisdom"
      :speed="digimon.speed"
      :weight="digimon.weight"
      :mistakes="digimon.mistakes"
      :bond="digimon.bond"
      :discipline="digimon.discipline"
      :wins="digimon.wins"
      :keyDigimon="digimon.keyDigimon"
      :keyPoints="digimon.keyPoints"
      :topPosition="digimon.topPosition"
      :leftPosition="digimon.leftPosition"
    />
    <evolveConstraint
      v-for="digimon in gen6"
      :key="digimon.id"
      :name="digimon.name"
      :generation="digimon.generation"
      :hp="digimon.hp"
      :mp="digimon.mp"
      :strength="digimon.strength"
      :stamina="digimon.stamina"
      :wisdom="digimon.wisdom"
      :speed="digimon.speed"
      :weight="digimon.weight"
      :mistakes="digimon.mistakes"
      :bond="digimon.bond"
      :discipline="digimon.discipline"
      :wins="digimon.wins"
      :keyDigimon="digimon.keyDigimon"
      :keyPoints="digimon.keyPoints"
      :topPosition="digimon.topPosition"
      :leftPosition="digimon.leftPosition"
    />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import evolveConstraint from "~/components/evolveConstraint";

export default Vue.extend({
  layout: 'tree',
  components: {
    evolveConstraint
  },
  async asyncData({ app, route }) {
    const data = await app.$axios.$get(
      `http://localhost:3000/digimons/${route.params.id}/tree`
    );
    const concated = data.digimons.concat(data.baseDigimon);
    const gen1 = concated
      .filter((digimon: any) => digimon.generation === "幼年期1")
      .map((digimon: any, idx: number) => {
        digimon.topPosition = `${idx * 450}px`;
        digimon.leftPosition = "0px";
        return digimon;
      });
    const gen2 = concated
      .filter((digimon: any) => digimon.generation === "幼年期2")
      .map((digimon: any, idx: number) => {
        digimon.topPosition = `${idx * 450}px`;
        digimon.leftPosition = "500px";
        return digimon;
      });
    const gen3 = concated
      .filter((digimon: any) => digimon.generation === "成長期")
      .map((digimon: any, idx: number) => {
        digimon.topPosition = `${idx * 450}px`;
        digimon.leftPosition = "1000px";
        return digimon;
      });
    const gen4 = concated
      .filter((digimon: any) => digimon.generation === "成熟期")
      .map((digimon: any, idx: number) => {
        digimon.topPosition = `${idx * 450}px`;
        digimon.leftPosition = "1500px";
        return digimon;
      });
    const gen5 = concated
      .filter((digimon: any) => digimon.generation === "完全体")
      .map((digimon: any, idx: number) => {
        digimon.topPosition = `${idx * 450}px`;
        digimon.leftPosition = "2000px";
        return digimon;
      });
    const gen6 = concated
      .filter((digimon: any) => digimon.generation === "究極体")
      .map((digimon: any, idx: number) => {
        digimon.topPosition = `${idx * 450}px`;
        digimon.leftPosition = "2500px";
        return digimon;
      });

    return {
      data,
      gen1,
      gen2,
      gen3,
      gen4,
      gen5,
      gen6
    };
  }
});
</script>

<style scoped>
.parent {
  position: relative;
  width: 2700px;
}
</style>
