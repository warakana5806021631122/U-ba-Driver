<template>
  <div class="hello">
    <section class="hero is-fullheight" style="background-color : #666666">
      <div class="hero" >
        <br><br>
        <div class="container">
          <div class="columns is-centered">
            <div class="column is-6 box">
              <br>
              <div class="columns is-centered">
                <div class="column is-6">
                  <label class="title is-3">ราคารวม  </label>
                  <span class="tag is-danger is-large">
                    <label class="title is-3" style="color : #ffffff">{{back}} ฿</label>
                  </span><br>
                  <br><br>
                  <img src="https://media.giphy.com/media/l2QDVwaaqvZGr834c/giphy.gif" alt="" width="100%"> <br>
                  <router-link to="/start">
                    <button type="button" name="button" style="width : 100%" class="button is-large is-success" @click="update()">จ่ายเงิน</button>
                  </router-link>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex'
export default {
  name: 'summary',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  computed: {
    ...mapGetters([
      'sec',
      'money',
      'caller'
    ]),
    back () {
      this.setCaller()
      return this.caller.cost
    }
  },
  methods: {
    ...mapActions([
      'bindtimerRef',
      'unbindtimerRef',
      'setTime',
      'updateState',
      'updateTimeCost',
      'setCaller'
    ]),
    update () {
      this.updateState({
        ID: this.caller.firebaseID,
        state: 'no wait'
      })
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
