<script setup lang="ts">
// export default{
//     props: {
//         numero: Object
//     }
//}
const props = defineProps({
    numero: Number
});
</script>
<template>
    <p>Numero:{{ numero }}</p>
</template>