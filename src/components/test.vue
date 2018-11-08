<template>
 <div class="test">
     <input type="text" v-model="title"> <br />
     <h1>{{title}}</h1>
     <p>{{user.firstName}}</p>
     <p v-text="user.firstName"></p>

     <ul>
         <li v-for="item in items"> {{ item.title }} </li>
     </ul>
     <button v-on:click="greet('Queenie')">Hello</button>
     <br/>
     <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="hitEnter">
     <br/>
     <label>First Name</label><input type="text" v-model="user.firstName">
     <br/>
     <label>First Name</label><input type="text" v-model="user.lastName">
     <h3>{{fullName}}</h3>
 </div>
</template>

<script>
  export default{
      name:'test',
      data(){
          return{
              title:"Hello World",
              user:{
                  firstName:"Queenie",
                  lastName:"Kun"
              },
              items: [
                  { title: "item One" },
                  {title:"item Two"},
                  {title:"Item Three"}
              ]
          }
      },
      methods:{
          greet: function(hi) {
              alert(hi);
          },
          pressKey: function(e) {
              console.log(e.target.value);   
          },
          hitEnter: function() {
              console.log('you hit enter');
              
          }
      },
      computed:{
          fullName: function() {
              return this.user.firstName + ' ' + this.user.lastName
          }
      }

  }
</script>

<style>
</style>