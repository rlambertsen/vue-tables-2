<template>
        <pagination
                :options="props.optionsObj"
                :for="props.name"
                :vuex="props.vuex"
                :records="props.records"
                :per-page="props.perPage"
                v-model="props.page"
                @paginate="paginate"/>
</template>

<script>
    import Pagination from 'vue-pagi-vwi'

    export default {
        name: "MyPagination",
        components: {
            Pagination
        },
        props: ['props'],
        methods: {
            paginate(page) {
                this.$emit('paginate', this.props.page);
                return this.props.setPage(page)
            }
        }
    }
</script>
