<template>
  <div class="container">
    <div class="field">
      <label for="name" class="label">名前検索</label>
      <input class="input" type="text" v-model="name">
    </div>
    <div class="table-container">
      <table class="table is-striped is-hoverable">
        <thead>
          <tr>
            <th>id</th>
            <th>日本語名</th>
            <th>世代</th>
            <th>HP</th>
            <th>MP</th>
            <th>力強さ</th>
            <th>頑丈さ</th>
            <th>かしこさ</th>
            <th>素早さ</th>
            <th>重さ</th>
            <th>育成ミス</th>
            <th>キズナ</th>
            <th>しつけ</th>
            <th>戦闘勝利数</th>
            <th>キーデジモン</th>
            <th>必要項目</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="digimon in filtered" :key="digimon.id">
            <td>{{digimon.id}}</td>
            <td>{{digimon.name}}</td>
            <td>{{digimon.generation}}</td>
            <td>{{digimon.hp}}</td>
            <td>{{digimon.mp}}</td>
            <td>{{digimon.strength}}</td>
            <td>{{digimon.stamina}}</td>
            <td>{{digimon.wisdom}}</td>
            <td>{{digimon.speed}}</td>
            <td>{{digimon.weight}}</td>
            <td>{{digimon.mistakes}}</td>
            <td>{{digimon.bond}}</td>
            <td>{{digimon.discipline}}</td>
            <td>{{digimon.wins}}</td>
            <td>{{digimon.keyDigimon}}</td>
            <td>{{digimon.keyPoints}}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
  
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  async asyncData({ app }) {
    const data = await app.$axios.$get("http://localhost:3000/digimons");
    return {
      data
    };
  },
  data () {
    return {
      name: ''
    }
  },
  computed: {
    filtered() {
      return this.$data.data.filter((digimon: any) => digimon.name.includes(this.$data.name))
    }
  }
});
</script>

<style>
</style>
