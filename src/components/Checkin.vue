<template>
    <div>
        <LvButton @click="signInComponent" :push="true" :raised="true" :deep-shadow="true" :deep-shadow-hover="true" :rounded="true"
            label="Jeg er på jobb" type="button" size="xl" />
    </div>
    <div>
        <LvButton @click="signOutComponent" :push="true" :raised="true" :deep-shadow="true" :deep-shadow-hover="true" :rounded="true"
            label="Jeg drar fra jobb" type="button" size="xl" />
    </div>
</template>

<script lang="ts">
import LvButton from 'lightvue/button'
import moment from 'moment'
import { google } from 'googleapis';
import { defineComponent } from 'vue';
import {authorize,getNextAvailableRow} from 'src/assets/index.js'
export default defineComponent({
    name: "Checkin",
    components: { LvButton },
    setup() {
        const getNumRows = authorize().then()
        const signInComponent = signIn;
        const signOutComponent = signOut;
        return {
            signInComponent,
            signOutComponent
        }
    }
})

</script>