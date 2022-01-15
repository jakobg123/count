<template>
    <div class="Counter">
        <div class="Counter__FormGroup">
            <label for="loan">Lån</label>
            <input
                class="Counter__InputText"
                id="loan"
                name="loan"
                type="text"
                v-model="loan.numbers"
            />
            <input
                type="range"
                v-model="loan.numbers"
                :min="loan.range.min"
                :max="loan.range.max"
                :step="loan.range.step"
            />
            <h1>{{ formattedLoan }}</h1>
        </div>
        <div class="Counter__FormGroup">
            <label for="downPayment">Kontantinsats</label>
            <input
                class="Counter__InputText"
                id="downPayment"
                name="downPayment"
                type="text"
                v-model="downPayment.numbers"
            />
            <input
                type="range"
                v-model="downPayment.numbers"
                :min="downPayment.range.min"
                :max="downPayment.range.max"
                :step="downPayment.range.step"
            />
            <h1>{{ formattedDownPayment }}</h1>
        </div>
        <div class="">
            <h3>{{ percentageOfLoan }}</h3>
        </div>
    </div>
</template>

<script>
export default {
    name: "Counter",
    data() {
        return {
            loan: {
                numbers: 4000000,
                range: {
                    min: 0,
                    max: 6000000,
                    step: 10000,
                },
            },
            downPayment: {
                numbers: 800000,
                range: {
                    min: 0,
                    max: 1500000,
                    step: 50000,
                },
            },
            // numbers: {
            //     loan: 4000000,
            //     downPayment: 800000,
            // },
            // range: {
            //     min: 0,
            //     max: 6000000,
            //     step: 10000,
            // },
        };
    },
    computed: {
        formattedLoan() {
            return this.loan.numbers
                .toString()
                .replace(/(\d)(?=(\d{3})+(?!\d))/g, "$1,");
        },
        formattedDownPayment() {
            return this.downPayment.numbers
                .toString()
                .replace(/(\d)(?=(\d{3})+(?!\d))/g, "$1,");
        },
        percentageOfLoan() {
            const totalSum = parseInt(this.downPayment.numbers) + parseInt(this.loan.numbers)
            const percentage = parseInt((this.downPayment.numbers / totalSum) * 100);
            return (
                percentage + " % av " + totalSum.toString().replace(/(\d)(?=(\d{3})+(?!\d))/g, "$1,")
            );
        },
    },
};
</script>

<style lang="scss">
.Counter {
    // border: 1px solid red;
    display: flex;
    flex-direction: column;
    align-items: center;

    &__FormGroup {
        display: flex;
        flex-direction: column;
        width: 50%;
    }

    &__InputText {
        padding: 1rem 1.5rem;
        font-size: 1rem;
    }
}
</style>
