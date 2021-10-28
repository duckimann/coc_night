<template>
    <div class="wd borderP7em">
        <div class="popupHeader">
            <h3>{{ popupName }}</h3>
            <h3 class="closeBtn borderP7em cPointer border2s0">X</h3>
        </div>
        <div class="popupBody borderP7em" align="center">
            <br />
            <Camps />
            <br />
            <div class="powerUps">
                <div class="troopBoost borderP7em cPointer border2s0" @click="boostTroops">
                    <h3>Boost Army</h3>
                </div>
            </div>
            <br />
            <TroopList />
        </div>
    </div>
</template>
<style scoped>
.border2s0 {
    border: 2px solid #000;
}

.wd {
    position: relative;
    border: 1px solid #000;
    background: var(--bgColor1);
    width: 60%;
    aspect-ratio: 1 / 0.5;
}
h3 {
    margin-block-end: 0 !important;
    margin-block-start: 0 !important;
    font-weight: bolder;
    color: #fff;
    text-shadow: 0px 2px #000, 0px 4px #000;
}
.popupHeader {
    position: relative;
    width: 100%;
    height: 6vh;
    top: 2%;
    display: flex;
    align-content: center;
    justify-content: center;
}
.closeBtn {
    position: absolute;
    right: 0.3rem;
    top: -0.5rem;
    padding: 0.4rem 0.7rem;
    background: #ea1415ff;
}
.popupBody {
    position: relative;
    z-index: 999;
    width: 99%;
    aspect-ratio: 1 / 0.45;
    /* height: calc(100% - 7vh); */
    left: 50%;
    transform: translate(-50%);
    background: #e8e8e0ff;
    margin-bottom: 1%;
}
.powerUps {
    position: relative;
    height: 10%;
    width: 97%;
}
.powerUps > div {
    position: relative;
    padding: 0.1rem 0.4rem;
    width: 17%;
    float: left;
    box-shadow: 0 0.2rem var(--shadowColor1);
    background: #836df2ff;
}
.powerUps > div > h3 {
    position: relative;
    width: min-content;
    float: left;
    left: 10%;
}
</style>
<script>
export default {
    props: ["popupName"],
    methods: {
        boostTroops() {
            alert("WIP - Boost Troops");
        }
    }
};
</script>
