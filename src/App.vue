<template>
<!--  <h2>This is Axios Get Api</h2>-->
<!--  <div v-for="data in posts" :key="data.id">-->
<!--  <p>ID:{{data.id}}</p>-->
<!--  <p>Title:{{data.title}}</p>-->
<!--  <p>Body:{{data.body}}</p>-->
<!--  </div>-->


  <h2>This is Post Api</h2>
  <form @submit.prevent="submitPost">
    <div>
      <label for="UserID">User ID :</label>
        <input type="text"  id="userID" v-model="postData.userID"/>
    </div>
    <div>
      <label for="title">Title :</label>
      <input type="text"  id="title" v-model="postData.title"/>
    </div>
    <div>
      <label for="body">Body :</label>
      <input type="text"  id="body" v-model="postData.body"/>
    </div>
    <button>Submit Button</button>
  </form>
</template>

<script>
import axios from 'axios'

export default {
  // This is Get Api
  // data(){
  //   return{
  //     posts:[],
  //   }
  // },
  // mounted() {
  //   axios.get('https://jsonplaceholder.typicode.com/posts/')
  //   .then(response=>this.posts=response.data)
  // }
  //Get Api End

  //Post Api Start
  data(){
    return{
      postData:{
        userID: '',
        title :'',
        body :'',
      }
    }
  },
  methods:{
    submitPost(){
      axios.post('https://jsonplaceholder.typicode.com/posts/',this.postData)
      .then(response=>console.log(response))
      // .then(response=>this.postData=response.data)
    }
  }
}

//POST Start End
</script>

<style>

</style>
