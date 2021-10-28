<template>
    <div class="container">
        <Popup popupName="Fill Army Camps" />
    </div>
</template>
<style>
:root {
    --bp7em: 0.7em;
    --shadowColor1: #a4a49eff;
    --shadowColor2: #f6f6f3ff;
    --bgColor1: #5e5451ff;
    --bgColor2: #d3d3cbff;
}
.customScrollBar::-webkit-scrollbar {
    width: 5%;
    height: 0.6%;
}
.customScrollBar::-webkit-scrollbar-track {
    background-color: transparent;
}
.customScrollBar::-webkit-scrollbar-thumb {
    background: #191919;
}

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
.borderP7em {
    border-radius: var(--bp7em);
}
.cPointer {
    cursor: pointer;
}
</style>
<script>
import Popup from "@/components/Popup.vue";
export default {
    components: { Popup }
};
</script>
