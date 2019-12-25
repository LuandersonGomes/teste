<template>
      <md-table-row>
        <md-table-cell md-numeric>{{id}}</md-table-cell>
        <md-table-cell>{{numeroProcesso}}</md-table-cell>
        <md-table-cell>{{estado}}</md-table-cell>
        <md-table-cell>{{fase}}</md-table-cell>
        <md-table-cell>{{valor}}</md-table-cell>
        <md-table-cell>{{status}}</md-table-cell>
        <md-table-cell>{{dataPublicacao}}</md-table-cell>
        <md-table-cell>{{dataEncerramento}}</md-table-cell>
      </md-table-row>
</template>
<script>
    export default {
        name: "TabelaProcessos",
        props: {
            id: {
                type: String
            },
            numeroProcesso: {
                type: String,
                required: true
            },
            estado: {
                type: String
            },
            fase: {
                type: String
            },
            valor: {
                type: String
            },
            status: {
                type: String
            },
            dataPublicacao: {
                type: String
            },
            dataEncerramento: {
                type: String
            }
        }
    }
</script>

<style scoped>

</style>
