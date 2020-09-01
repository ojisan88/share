<template>
  <div>
    <HeaderAuth />
    <div class="card">
     <p>ログイン</p>
     <div class="form">
      <input type="email" placeholder="メールアドレス" v-model="email" />
      <input type="password" placeholder="パスワード" v-model="password" />
      <button @click="auth">ログイン</button>
     </div>
    </div>
  </div>
</template>

<script>
import HeaderAuth from "../components/HeaderAuth"
export default {
  data(){
    return{
      email:"",
      password:""
    };
  },
  components:{
    HeaderAuth
  },
  methods:{
    auth(){
      this.$store.dispatch("login" , {
        email: this.email,
        password:this.password
      });
    }
  }
};
</script>

<style scoped>
button{
  background-color: #5419da;
  border-radius: 25px;
  color: #ffffff;
  cursor: pointer;
  width: 100px;
  text-align: center;
  padding: 8px 0 10px;
}
.card{
  margin: 100px auto;
  width: 350px;
  background-color: #ffffff;
  border-radius: 5px;
  padding: 20px;
}
.card p{
  color: black;
  font-weight: bold;
  text-align: center;
}
input{
  border-radius: 10px;
  width: 80%;
  margin-top: 15px;
  padding: 10px;
  border: 1px solid black;
  color: black;
}
.form{
  text-align: center;
}
.form button{
  margin-top: 15px;
}
</style>