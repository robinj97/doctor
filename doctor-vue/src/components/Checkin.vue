<template>
    <div>
        <LvButton
     :push="true"
     :raised="true"
     :deep-shadow="true"
     :deep-shadow-hover="true"
     :rounded="true"
     label="Jeg er på jobb"
     type="button"
     size="xl"
 />
    </div>
    <div>
        <LvButton
     :push="true"
     :raised="true"
     :deep-shadow="true"
     :deep-shadow-hover="true"
     :rounded="true"
     label="Jeg drar fra jobb"
     type="button"
     size="xl"
 />
    </div>
</template>

<script lang="ts">
import LvButton from 'lightvue/button';
import { defineComponent } from 'vue';
export default defineComponent({
    name: "Checkin",
    components: {LvButton},
    setup() {
        function checkIn() {
            return;
        }

        function checkOut() {
            return;
        }
        return {
            checkIn,
            checkOut
        }
    }
})

</script>