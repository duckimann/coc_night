<template>
    <div class="troop">
        <div class="img">
            <img
                :src="require(`@/static/${name}.png`)"
                :alt="name"
                @click="addTroop"
            />
        </div>
        <div :class="['top_right', 'cPointer', 'borderP7em', inCamp ? 'inCamp' : 'notInCamp']">
            <h3 v-if="!inCamp" @click="troopInfo">i</h3>
            <h3 v-if="inCamp" @click="rmTroop">-</h3>
        </div>
        <div :class="['bottom_left', 'borderP7em', lv == 18 ? 'bl_maxed' : '']">
            <h3>{{ lv }}</h3>
        </div>
    </div>
</template>
<style scoped>
.troop {
    position: relative;
    background: #58a6d4ff;
    margin: 0;
    padding: 2px;
    border-radius: 1em;
    box-shadow: 0px 5px #285478ff;
}
.top_right {
    position: absolute;
    top: 0;
    right: 0;
    padding: 0 7px;
    margin: 5px 5px 0 0;
    border: 2px solid #000;
    width: fit-content;
}
.inCamp {
    background: #de100eff;
}
.notInCamp {
    background: #3574c2ff;
}
.top_right > h3 {
    text-shadow: 0px 2px #000;
    font-size: 1.5em;
}
.bottom_left {
    position: absolute;
    bottom: 0;
    left: 0;
    padding: 5px;
    margin: 0 0 5px 5px;
    border: 1px solid #000;
    background: #000;
    width: fit-content;
}
.bl_maxed {
    background: #f7b858ff !important;
    border-color: #eddaabff;
}
.img {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    height: 100%;
}
.img > img {
    height: 100%;
}
h3 {
    margin-block-end: 0 !important;
    margin-block-start: 0 !important;
    font-weight: bolder;
    color: #fff;
    text-shadow: 0px 2px #000, 0px 4px #000;
}
</style>
<script>
export default {
    props: {
        lv: Number,
        inCamp: Boolean,
        name: String
    },
    methods: {
        troopInfo() {
            alert("WIP - Troop Info");
        },
        rmTroop() {
            $nuxt.$emit("rm-troop", this.$parent.cano);
        },
        addTroop() {
            if (!this.inCamp) {
                $nuxt.$emit("add-troop", this.name);
            }
        }
    }
};
</script>
