<template>
    <div class="wd">
        <div class="popupHeader">
            <h3>{{ popupName }}</h3>
            <h3 class="closeBtn">X</h3>
        </div>
        <div class="popupBody" align="center">
            <br />
            <Camps />
            <br />
            <div class="powerUps">
                <div class="troopBoost" @click="boostTroops">
                    <h3>Boost Army</h3>
                </div>
            </div>
            <br />
            <TroopList />
        </div>
    </div>
</template>
<style scoped>
.wd {
    position: relative;
    border: 1px solid #000;
    border-radius: 0.7em;
    background: #5e5451ff;
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
    border-radius: 0.7em;
    border: 2px solid #000;
    right: 0.3rem;
    top: -0.5rem;
    padding: 0.4rem 0.7rem;
    background: #ea1415ff;
    cursor: pointer;
}
.popupBody {
    position: relative;
    z-index: 999;
    width: 99%;
    aspect-ratio: 1 / 0.45;
    /* height: calc(100% - 7vh); */
    left: 50%;
    transform: translate(-50%);
    border-radius: 0.7em;
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
    border-radius: 0.7em;
    box-shadow: 0 0.2rem #a4a49eff;
    border: 2px solid #000;
    background: #836df2ff;
    cursor: pointer;
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
