<template>
  <div class="home row">
    <div class="col-md-3">
      <span class="hipster img-fluid rounded"></span>
    </div>
    <div class="col-md-9">
      <h1 class="display-4">DossierFacile.ma</h1>
      <p class="lead">Le dossier numérique de tracabilité</p>

      <div>
        <div class="alert alert-success" v-if="authenticated">
          <span v-if="username">Vous êtes connecté en tant que "{{ username }}"</span>
        </div>

        <div class="alert alert-warning" v-if="!authenticated">
          <span>Si vous voulez vous </span>
          <a class="alert-link" v-on:click="openLogin()">connecter</a
          ><span
            >, vous pouvez essayer les comptes par défaut:<br />- Administrateur (login="admin" et password="admin") <br />- Utilisateur
            (login="user" et password="user").</span
          >
        </div>
        <div class="alert alert-warning" v-if="!authenticated">
          <span>Vous n'avez pas encore de compte?</span>&nbsp;
          <router-link class="alert-link" to="/register">Enregistrer un nouveau compte</router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slide: 0,
      sliding: null,
    };
  },
  methods: {
    onSlideStart() {
      this.sliding = true;
    },
    onSlideEnd() {
      this.sliding = false;
    },
  },
};
</script>

<script lang="ts" src="./home.component.ts"></script>
