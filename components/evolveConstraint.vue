<template>
  <div class="constraintParent box">
    <h1 class="title is-5">{{name}}</h1>
    <div class="columns">
      <div class="column is-3">HP</div>
      <div class="column is-3">{{hp}}</div>
      <div class="column is-3">MP</div>
      <div class="column is-3">{{mp}}</div>
    </div>
    <div class="columns">
      <div class="column is-3">力強さ</div>
      <div class="column is-3">{{strength}}</div>
      <div class="column is-3">頑丈さ</div>
      <div class="column is-3">{{stamina}}</div>
    </div>
    <div class="columns">
      <div class="column is-3">賢さ</div>
      <div class="column is-3">{{wisdom}}</div>
      <div class="column is-3">素早さ</div>
      <div class="column is-3">{{speed}}</div>
    </div>
    <div class="columns">
      <div class="column is-3">体重</div>
      <div class="column is-3">{{weight}}</div>
      <div class="column is-3">育ミス</div>
      <div class="column is-3">{{mistakes}}</div>
    </div>
    <div class="columns">
      <div class="column is-3">キズナ</div>
      <div class="column is-3">{{bond}}</div>
      <div class="column is-3">しつけ</div>
      <div class="column is-3">{{discipline}}</div>
    </div>
    <div class="columns">
      <div class="column is-3">勝利</div>
      <div class="column is-3">{{wins}}</div>
    </div>
    <div class="columns">
      <div class="column is-5">キーデジモン</div>
      <div class="column is-7">{{keyDigimon}}</div>
    </div>
    <div class="columns">
      <div class="column is-3"></div>
      <div class="column is-3"></div>
      <div class="column is-3">項目数</div>
      <div class="column is-3">{{keyPoints}}</div>
    </div>
  </div>
  
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: {
    name: { type: String, required: true },
    hp: { type: String, required: true },
    mp: { type: String, required: true },
    strength: { type: String, required: true },
    stamina: { type: String, required: true },
    wisdom: { type: String, required: true },
    speed: { type: String, required: true },
    weight: { type: String, required: true },
    mistakes: { type: String, required: true },
    bond: { type: String, required: true },
    discipline: { type: String, required: true },
    wins: { type: String, required: true },
    keyDigimon: { type: String, required: true },
    keyPoints: { type: String, required: true },
    topPosition: { type: String, required: true},
    leftPosition: { type: String, required: true}
  },
  mounted() {
    console.log(this.$props)
    this.$el.style.top = this.$props.topPosition
    this.$el.style.left = this.$props.leftPosition
  }
});
</script>

<style scoped>
.constraintParent {
  position: absolute;
  width: 300px;
  font-size: 0.8em;
}
</style>