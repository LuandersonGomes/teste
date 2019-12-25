<template>
  <div id="app">
    <div id="nav" v-if="authenticated">
        <md-toolbar class="md-large md-primary">
          <div class="md-toolbar-row">
            <div class="md-toolbar-section-start">
                <h1>Processos</h1>
            </div>
            <div class="md-toolbar-section-end">

                <router-link v-if="authenticated" to="/login" v-on:click.native="logout()" replace>Sair</router-link>


              <md-button class="md-icon-button">
              </md-button>
            </div>
          </div>
        </md-toolbar>
    </div>
    <router-view @authenticated="setAuthenticated" />
  </div>
</template>

<script>
    export default {
        name: 'App',
        data() {
            return {
                authenticated: false,
                mockAccount: {
                    email: 'gomesluanderson@gmail.com',
                    senha: '123456'
                }
            }
        },
        mounted() {
            if(!this.authenticated) {
                this.$router.replace({ name: 'login' });
            }
        },
        methods: {
            setAuthenticated(status) {
                this.authenticated = status;
            },
            logout() {
                this.authenticated = false;
            }
        }
    }
</script>

<style>
  body {
    background-color: #F0F0F0;
  }
  #app {
    width: 100%;
    margin: auto;
  }
</style>
