<template>
    <div class="camps borderP7em customScrollBar">
        <camp v-for="(name, index) of camps" :name="name" :cano="index" />
    </div>
</template>
<style scoped>
.camps {
    display: flex;
    overflow-y: hidden;
    overflow-x: auto;
    padding: 0.3rem 0.5rem 0.7rem 0.5rem;
    width: 97%;
    height: 50%;
    background: var(--bgColor2);
    box-shadow: 0 -0.2rem var(--shadowColor1), 0 0.2rem var(--shadowColor2);
}
</style>
<script>
import { troop_list, camps } from "@/asset/sample.js";
import Camp from "./Camp.vue";
export default {
    components: { Camp },
    data() {
        let localCamp = localStorage.getItem("camps");
        if (localCamp) localCamp = JSON.parse(localCamp);
        return {
            troop_list,
            camps: localCamp ? localCamp : camps
        };
    },
    created() {
        this.$nuxt.$on("add-troop", this.addTroop);
        this.$nuxt.$on("rm-troop", this.rmTroop);
    },
    methods: {
        rmTroop(campNo) {
            this.$set(this.camps, campNo, "");
        },
        addTroop(troopName) {
            this.$set(this.camps, this.camps.indexOf(""), troopName);
            // this.camps.splice(this.camps.indexOf(""), 1, troopName);
        }
    },
    watch: {
        camps() {
            localStorage.setItem("camps", JSON.stringify(this.camps));
        }
    }
};
</script>
