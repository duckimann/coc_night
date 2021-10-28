<template>
    <div class="troopList borderP7em customScrollBar">
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
    background: var(--bgColor2);
    box-shadow: 0 -0.2rem var(--shadowColor1), 0 0.2rem var(--shadowColor2);
    height: 20%;
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
