<template>
  <div id="app">
    <div class="menu">
      <h1>Oracle Of Bacon</h1>
    </div>
    <actor-search id="actor-search" v-on:search="consultOracle" v-on:getsome="getOracle"  ></actor-search>
    <search-result id="result" :actor-name="actorName" :get-some="getSome"></search-result>
    <last-10-searches id="last-10-searches" class="box"></last-10-searches>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ActorSearch from "./components/ActorSearch.vue";
import SearchResult from "./components/SearchResult.vue";
import Last10Searches from "./components/Last10Searches.vue";

export default defineComponent({
  name: "app",
  data() {
    return {
      actorName: "",
      getSome:"",
    };
  },
  components: {
    ActorSearch,
    SearchResult,
    Last10Searches,
  },
  methods: {
    consultOracle(actorName: string) {
      this.actorName = actorName;
    },
    getOracle(actorName: string) {
      this.getSome = this.getSome + 'a';
    },
  },
});
</script>

<style>
h3,
p,
ol {
  text-align: center;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  color: #37403f;
}

h1 {
  text-align: left;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  color: #bbcba4;
  padding-left: 10px;
}

.box {
  padding: 0px 5px 0px 5px;
  margin: 30px;
  background-color: #e8eaea;
  border: solid;
  width: -webkit-fit-content;
  height: -webkit-fit-content;
  width: -moz-fit-content;
  height: -moz-fit-content;
  border: none;
  margin-left: auto;
  margin-right: auto;
}

.menu {
  background-color: #317347;
  color: #fbffc3;
  position: absolute;
  width: 100%;
  margin: 0px Opx Opx 1opx;
  top: 0px;
  right: 0px;
}

body {
  background: url(./assets/kevin-bacon-background-left.png) no-repeat;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}

#last-10-searches {
  position: absolute;
  background-color: #fbf3c2;
  top: 220px;
  right: 50px;
}

#connected-user {
  position: absolute;
  top: 20px;
  right: 20px;
}

*:focus {
  outline: none;
}

body {
  margin-top: 120px;
}
</style>
