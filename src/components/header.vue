<template>
  <div class='cccc'>
    <div class="navbar is-transparent is-info"  style="height: 100px">
      <div class="navbar-brand">
        <div class="navbar-item">
          <label class="title is-2" style="color : #FFFFFF">U-ba Driver</label>
        </div>
      </div>

      <div class="navbar-end">
        <div class="navbar-item">
          
          <div v-if="!isReady">
            <img :src="user.fb.photoURL" alt="">
            {{user.displayName}}
          </div>
          <div v-if="!isReady">
            <router-link to="/">
              <button type="button" class="button is-danger" name="button" @click="discon()">Log out</button>
            </router-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex'
export default {
  computed: {
    ...mapGetters([
      'user',
      'isReady'
    ])
  },
  methods: {
    ...mapActions([
      'logout',
      'binddriverRef',
      'unbinddriverRef'
    ]),
    discon () {
      this.logout()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
