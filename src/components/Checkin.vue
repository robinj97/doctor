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
    <p>Does this work</p>
</template>

<script lang="ts">
import LvButton from 'lightvue/button' 
import moment from 'moment'
import * as ExcelJS from 'exceljs';
import { defineComponent } from 'vue';
export default defineComponent({
    name: "Checkin",
    components: {LvButton},
    setup() {
        return {
        }
    }
})

</script>