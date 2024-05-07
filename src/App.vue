<template>
  <h1>{{title}}</h1>
  <div v-if="showModal">
    <modal  theme ="sale" @close="openModal">
      <template v-slot:links>
        <a href="">Sign up now</a>
        <a href="">More info</a>
      </template>
      <h1>Ninja Give aways</h1>
      <p>Grab your Ninja Swag for half price!</p>
    
    </modal>
  </div>


  <div v-if="showModal2">
    <modal  theme ="sale" @close="openModal2">
      
      <h1>Sign up to the news lette</h1>
      <p>For updates and promocode!</p>
    
    </modal>
  </div>

  <button @click="openModal2">Promocode</button>  
  <!-- <input type="text" ref="name"> -->

  <!-- <button @click="handleclick">Click me</button> -->
  <table>
    <thead>
      <tr>
        <th>Author</th>
        <th>Age</th>
        <th>Url</th>
        <th>Action</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="book in books">
        <td v-if="book.author">{{ book.author }}</td>
        <td>{{ book.age }}</td>
        <td>{{ book.url }}</td>
        <td><button class="action-button" @click="openModal">View</button></td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <th>Author</th>
        <th>Age</th>
        <th>Url</th>
        <th>Action</th>
      </tr>
    </tfoot>
  </table>

  <p @click="callonClick"> {{ footer }}</p>
</template>


<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  components:{Modal},
  data(){
    return{
      showModal:false,
      showModal2:false,
      text:"Grab the Give away at a throw away pricing in kenya ",
      header :"View Details ",
      footer:"Created By Gideon Kiprono",
      title:"List of Authors",
      books:[
      {author:"Solomon Engineer",age:45,url:"wwww.test.com"},
      {author:"Gideon Kiprono",age:45,url:"wwww.test.com"},
      {author:"Joseph Kebenei",age:45,url:"wwww.joseph.com"},
      ]
    }
  },
  methods:{
    changeTitle(){
      this.title ="this is test element Creation"
    },
    callonClick(){
      this.changeTitle()
    },
    handleclick(){
      console.log(this.$refs.name)
      this.$refs.name.focus()
    },
    loadmodal(){
      alert("testing")
    },
    openModal(){
     this.showModal =!this.showModal 
    },
    openModal2(){
     this.showModal2 =!this.showModal2 
    }


  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
/* Basic Table Styles */
/* Basic Table Styles */
table {
  margin-left: auto;
  margin-right: auto;
  width: 50%;
  border-collapse: collapse;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.1); /* Adding a subtle shadow */
  border-radius: 8px; /* Rounded corners for a softer look */
}

th, td {
  margin:0;
  padding: 12px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

/* Table Header Styles */
thead {
  background-color: #f8f9fa; /* Light gray background */
  border-top-left-radius: 8px;
  border-top-right-radius: 8px;
}

th {
  background-color: #4CAF50;
  color: white;
}

/* Table Body Styles */
tbody tr:nth-child(even) {
  background-color: #f2f2f2;
  margin: 0;
}

/* Table Footer Styles */
tfoot {
  background-color: #4CAF50;
  color: white;
  border-bottom-left-radius: 8px;
  border-bottom-right-radius: 8px;
}

/* Hover Effect */
tbody tr:hover {
  background-color: #e9ecef; /* Lighter background on hover */
}

.action-button {
  display: inline-block;
  padding: 10px 20px;
  font-size: 16px;
  font-weight: bold;
  text-align: center;
  text-decoration: none;
  cursor: pointer;
  border: none;
  border-radius: 4px;
  background-color: #4CAF50; /* Green */
  color: white;
  transition: background-color 0.3s ease;
}

.action-button:hover {
  background-color: #45a049; /* Darker shade of green on hover */
}

.modal .actions{
    text-align: center;
    margin: 30p 0 10px 0;
    color: #333;

}

.modal .actions a{
    color :#333;
    padding :8px;
    border:1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin:10px ;
}


</style>
