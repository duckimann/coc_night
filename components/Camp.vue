<template>
    <div class="camp borderP7em">
        <div :class="['campNo', name ? '' : 'campNo_noTroop']">
            <h3>Camp {{ cano + 1 }}</h3>
        </div>
        <div v-if="typeof troop_list[inList[name]] === 'object'" class="smCamp">
            <troop
                :name="troop_list[inList[name]].name"
                :lv="troop_list[inList[name]].lv"
                :inCamp="true"
            />
        </div>

        <div v-if="typeof troop_list[inList[name]] === 'object'" class="inCamp">
            <h3>{{ troop_list[inList[name]].perCamp }}</h3>
        </div>
    </div>
</template>
<style scoped>
.camp {
    height: 99%;
    aspect-ratio: 1 / 1.5;
    background: #e8e8e0ff;
    margin: 0.2em 0.3em 0 0.3em;
    box-shadow: 0 0.2rem var(--shadowColor1), 0 -0.2rem var(--shadowColor2);
}
.camp:first-child {
    margin-left: auto;
}
.camp:last-child {
    margin-right: auto;
}
.campNo {
    border-radius: var(--bp7em) var(--bp7em) 0 0;
    background: #83a851ff;
    color: #fff;
    padding: 0.5em;
}
.campNo_noTroop {
    background: var(--bgColor1) !important;
}
.smCamp {
    position: relative;
    width: 70%;
    aspect-ratio: 1 / 1;
    margin: 12%;
}
.troop {
    width: 100%;
    height: 100%;
}
.inCamp {
    position: relative;
    border-radius: 0.3em;
    background: var(--bgColor1);
    width: 80%;
    color: #fff;
}
</style>
<script>
import { troop_list } from "@/asset/sample.js";
import Troop from "@/components/Troop.vue";
export default {
    props: {
        name: String,
        cano: Number
    },
    components: { Troop },
    data() {
        return {
            troop_list
        };
    },
    created() {
        this.initList();
    },
    methods: {
        initList() {
            let table = {};
            for (let it = 0, len = troop_list.length; it < len; it++) {
                table[troop_list[it].name] = it;
            }
            this.inList = table;
        }
    }
};
</script>
