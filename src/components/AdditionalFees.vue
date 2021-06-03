<template>
    <div class="container-fluid additional-fee-container">
        <!-- <div class="input-group flex-nowrap">
            <span class="input-group-text">Description</span>
            <span class="input-group-text">Dollar Amount</span>
            <span class="input-group-text">Percentage Amount</span>
            <span class="input-group-text">Start Date</span>
            <span class="input-group-text">End Date</span>
        </div>
        <div class="input-group flex-nowrap" v-for="fee in fees" :key="fee.id">
                <input type="text" v-model="fee.description" placeholder="Description" class="form-control form-input">
                <input type="text" v-model="fee.dollarAmount" placeholder="Dollar Amount" class="form-control form-input">
                <input type="text" v-model="fee.percentageAmount" placeholder="Percentage Amount" class="form-control form-input">
                <input type="text" v-model="fee.startDate" placeholder="Start Date" class="form-control form-input">
                <input type="text" v-model="fee.endDate" placeholder="End Date" class="form-control form-input">
                <div class="col-sm-1">   
                    <i class="fas fa-minus-circle"></i>
                </div>  
        </div> -->
        <table class="table">
            <thead class="thead-dark">
                <tr>
                    <th></th>
                    <th scope="col">Description</th>
                    <th scope="col">Dollar Amount</th>
                    <th scope="col">Percentage Amount</th>
                    <th scope="col">Start Date</th>
                    <th scope="col">End Date</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="fee in fees" :key="fee.id">
                    <td><i class="fas fa-minus-circle"></i></td>
                    <td><input type="text" v-model="fee.description" placeholder="Description" class="form-control form-input"></td>
                    <td><input type="text" v-model="fee.dollarAmount" placeholder="Dollar Amount" class="form-control form-input"></td>
                    <td><input type="text" v-model="fee.percentageAmount" placeholder="Percentage Amount" class="form-control form-input"></td>
                    <td><input type="text" v-model="fee.startDate" placeholder="Start Date" class="form-control form-input"></td>
                    <td><input type="text" v-model="fee.endDate" placeholder="End Date" class="form-control form-input"></td>
                </tr>
            </tbody>
            <i class="fas fa-plus-circle" @click="handlePlusClick"></i>
        </table>
    </div>
</template>

<script>
export default {
    props: {
        fees: {
            type: Array,
        },
    },
    methods: {
        handlePlusClick() {
            this.fees.push({
                id: Math.max(...this.fees.map(fee => fee.id)) + 1,
                description: '',
                dollarAmount: '',
                percentageAmount: '',
                startDate: '',
                endDate: ''
            })
        }
    },
}
</script>

<style>
.additional-fee-container span,
.additional-fee-container input,
.additional-fee-container input::-webkit-input-placeholder {
    font-size: smaller;
}

.additional-fee-container span,
.input-group>.form-control {
    flex: 0 0 15%;
}

.additional-fee-container i {
    transform: translateY(50%);
}

.additional-fee-container table.table {
    width: 80%;
    margin-top: 50px;
}

</style>