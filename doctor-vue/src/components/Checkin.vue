<template>
    <div>
        <LvButton
    @click="signIn"
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
        @click="signOut"
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
import moment from 'moment'
import * as ExcelJS from 'exceljs';
import { defineComponent } from 'vue';
export default defineComponent({
    name: "Checkin",
    components: {LvButton},
    setup() {
        const workbook = new ExcelJS.Workbook();
        const sheetName = 'Sheet1';
        const fileName = '/Users/robin/Programming/doctor/doctor-vue/src/assets/records.xlsx';
        // const x = path.resolve('doctor-vue/src/assets/records.xlsx');
        async function signIn() {
            const date = moment().format('YYYY-MM-DD HH:mm:ss');

            await workbook.xlsx.readFile(fileName);
            const worksheet = workbook.getWorksheet(sheetName);

            // Get the last used row in the first column
            const lastRow = worksheet.getColumn(1).lastCell?.row || 1;

            // Write the sign-in timestamp to the next available row in the first column
            const row = worksheet.getRow(lastRow + 1);
            row.getCell(1).value = date;
            await workbook.xlsx.writeFile(fileName);

            console.log('Sign-in timestamp written to Excel file');
        }

        async function signOut() {
            const date = moment().format('YYYY-MM-DD HH:mm:ss');

            await workbook.xlsx.readFile(fileName);
            const worksheet = workbook.getWorksheet(sheetName);

            // Get the last used row in the second column
            const lastRow = worksheet.getColumn(2).lastCell?.row || 1;

            // Write the sign-out timestamp to the next available row in the second column
            const row = worksheet.getRow(lastRow + 1);
            row.getCell(2).value = date;
            await workbook.xlsx.writeFile(fileName);

            console.log('Sign-out timestamp written to Excel file');
        }
        return {
            signIn,
            signOut
        }
    }
})

</script>