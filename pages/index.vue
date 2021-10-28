<template>
    <div class="container">
        <Popup popupName="Fill Army Camps" />
    </div>
</template>
<style>
* {
    margin: 0;
    padding: 0;
    font-family: "Fira Code";
}
.container {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
<script>
import Popup from "@/components/Popup.vue";
export default {
    components: { Popup }
};
</script>
