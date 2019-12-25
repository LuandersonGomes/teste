<template>
  <form novalidate class="md-layout">
    <md-card class="md-layout-item md-size-50 md-small-size-100">
      <md-card-header>
        <div class="md-title">Login</div>
      </md-card-header>
      <md-card-content>
        <md-field>
          <label for="email">Email</label>
          <md-input type="email" name="email" id="email" autocomplete="email" v-model="input.email"
                    :disabled="sending"/>
        </md-field>
        <md-field>
          <label for="senha">Senha</label>
          <md-input type="password" name="senha" id="senha" autocomplete="email" v-model="input.senha"
                    :disabled="sending"/>
        </md-field>
      </md-card-content>
      <md-progress-bar md-mode="indeterminate" v-if="sending"/>
      <md-card-actions>
        <md-button class="md-primary" v-on:click="logar()" :disabled="sending">Login</md-button>
      </md-card-actions>
    </md-card>
  </form>
</template>

<script>
    export default {
        name: 'Login',
        data() {
            return {
                input: {
                    email: '',
                    senha: ''
                }
            }
        },
        methods: {
            logar() {
                if (this.input.email !== "" && this.input.senha !== "") {
                    if (this.input.email === this.$parent.mockAccount.email && this.input.senha === this.$parent.mockAccount.senha) {
                        this.$emit('authenticated', true);
                        this.$router.replace({name: 'dashboard'});
                    } else {
                        console.log('Usuario ou senha Incorreto');
                    }
                } else {
                    console.log('Usuario Logado');
                }
            }
        }
    }
</script>

<style scoped>

</style>
