<template>
    <div class="camp">
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
    border-radius: 0.7em;
    margin: 0.2em 0.3em 0 0.3em;
    box-shadow: 0 0.2rem #a4a49eff, 0 -0.2rem #f6f6f3ff;
}
.camp:first-child {
    margin-left: auto;
}
.camp:last-child {
    margin-right: auto;
}
.campNo {
    border-top-left-radius: 0.7em;
    border-top-right-radius: 0.7em;
    background: #83a851ff;
    color: #fff;
    padding: 0.5em;
}
.campNo_noTroop {
    background: #5e5451ff !important;
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
    background: #5e5451ff;
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
