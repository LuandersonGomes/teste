<template>
  <div>
    <md-table md-card>
      <md-table-row>
        <md-table-head md-numeric>ID</md-table-head>
        <md-table-head>Numero do Processo</md-table-head>
        <md-table-head>Estado</md-table-head>
        <md-table-head>fase</md-table-head>
        <md-table-head>Valor do Processo</md-table-head>
        <md-table-head>Status</md-table-head>
        <md-table-head>Publicação</md-table-head>
        <md-table-head>Encerramento</md-table-head>
      </md-table-row>
      <tabela-processos v-for="processos in processos"
                        v-bind:id="processos.id"
                        v-bind:numero-processo="processos.numeroProcesso"
                        v-bind:estado="processos.estado"
                        v-bind:fase="processos.fase"
                        v-bind:valor="processos.valorProcesso"
                        v-bind:status="processos.status"
                        v-bind:dataPublicacao="processos.dataPublicacao"
                        v-bind:dataEncerramento="processos.dataEncerramento"></tabela-processos>
    </md-table>
  </div>
</template>


<script>
    import axios from 'axios';
    import TabelaProcessos from '@/components/TabelaProcessos';

    export default {
        name: 'Dashboard',
        components: {TabelaProcessos},
        mounted() {
            axios
              .get('http://localhost:3000/processos')
              .then(response => (this.processos = response.data))
        },
        data() {
            return {
                processos: []
            }
        }
    }
</script>

<style scoped>
  #dashboard {
    background-color: #FFFFFF;
    border: 1px solid #CCCCCC;
    padding: 20px;
    margin-top: 10px;
  }
</style>
