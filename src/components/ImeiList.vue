<template>
    <table class="table is-striped is-fullwidth">
        <thead>
            <tr>
                <th>Imei No. <i class="fa fa-search" aria-hidden="true"></i></th>
                <th>Status</th>
                <th>Action</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="(row, index) in rows">
                <td>
                    <!--<input type="text" placeholder="Digite imei" v-model="row.imei" @onChange="validateImei(row)">-->
                    <input type="text" placeholder="Digite imei" v-model="row.imei">
                </td>
                <td>
                    <input type="text" v-model="row.status" disabled>
                </td>
                <td>
                    <a href="#" @click="removeRow(index)">
                        <i class="fa fa-trash" aria-hidden="true"></i>
                    </a>
                    <a href="#" @click="addRow">
                        <i class="fa fa-plus" aria-hidden="true"></i>
                    </a>
                </td>
            </tr>
        </tbody>
    </table>
</template>
<script>
export default {
    name: 'imei-list-template',
    data() {
        return {
            rows: [{
                imei: "3568680000414120",
                status: "Valid"
            }, {
                imei: "490154203237517",
                status: "Invalid"
            }]
        }
    },
    methods: {
        addRow: function() {
            this.rows.push({
                imei: "",
                status: ""
            });
        },
        removeRow: function(index) {
            this.rows.splice(index, 1);
        }
    }
}
</script>
