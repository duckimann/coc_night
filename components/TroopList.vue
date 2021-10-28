<template>
    <div class="troopList">
        <Troop
            v-for="tro of troop_list"
            :name="tro.name"
            :lv="tro.lv"
            :inCamp="false"
        />
    </div>
</template>
<style scoped>
.troopList {
    display: flex;
    overflow-y: hidden;
    overflow-x: auto;
    padding: 0.3rem 0.5rem 0.7rem 0.5rem;
    width: 97%;
    background: #d3d3cbff;
    border-radius: 0.7em;
    box-shadow: 0 -0.2rem #a4a49eff, 0 0.2rem #f6f6f3ff;
    height: 20%;
}
.troopList::-webkit-scrollbar {
    width: 5%;
    height: 0.6%;
}
.troopList::-webkit-scrollbar-track {
    background-color: transparent;
}
.troopList::-webkit-scrollbar-thumb {
    background: #191919;
}
.troop {
    margin: 0 0.2rem;
}
</style>
<script>
import { troop_list } from "@/asset/sample.js";
import Troop from "@/components/Troop.vue";
export default {
    components: { Troop },
    data() {
        return { troop_list };
    }
};
</script>
