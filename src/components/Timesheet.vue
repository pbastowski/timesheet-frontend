<template>
    <div>
        <v-data-table
            :headers="headers"
            :items="items"
            Xitems-per-page="15"
            class="elevation-1"
        >
            <template v-slot:item.date="{ item }">
                <v-text-field
                    style="width: 100px;"
                    type="date"
                    v-model="item.date"
                />
            </template>
            <template v-slot:item.worked="{ item }">
                <v-text-field type="number" v-model.number="item.worked" />
            </template>
            <template v-slot:item.internal="{ item }">
                <v-text-field type="number" v-model.number="item.internal" />
            </template>
            <template v-slot:item.courses="{ item }">
                <v-text-field type="number" v-model.number="item.courses" />
            </template>
            <template v-slot:item.leave="{ item }">
                <v-text-field type="number" v-model.number="item.leave" />
            </template>
            <template v-slot:item.sick="{ item }">
                <v-text-field type="number" v-model.number="item.sick" />
            </template>
            <template v-slot:item.doctor="{ item }">
                <v-text-field type="number" v-model.number="item.doctor" />
            </template>
        </v-data-table>
    </div>
</template>

<script>
export default {
    data: () => ({
        headers: [
            { text: 'date', value: 'date' },
            { text: 'worked', value: 'worked' },
            { text: 'internal hours', value: 'internal' },
            { text: 'courses', value: 'courses' },
            { text: 'leave', value: 'leave' },
            { text: 'sick', value: 'sick' },
            { text: 'doctor', value: 'doctor' }
            // { text: 'special_leave' },
            // { text: 'part_time_leave' },
            // { text: 'overtime_from' },
            // { text: 'overtime_to' },
            // { text: 'standby' }
        ]
    }),

    created() {
        // this.$store.dispatch('getTimesheet')
    },

    computed: {
        items() {
            return this.$store.state.timesheet.timesheet
        }
    }
}
</script>
