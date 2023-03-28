<template>
    <form style="background: white;"
     @submit.prevent="SignUp">
        <label>Name</label>
        <input v-model.trim="Formdata.name">
        <label>Surname</label>
        <input v-model.trim="Formdata.surname">
        <label>Age</label>
        <input v-model.trim="Formdata.age">
        <label>Email</label>
        <input v-model.trim="Formdata.email">
        <label>Favorite Framework</label>
        <select v-model.trim="Formdata.FF">
            <option value="Vue">Vue</option>
            <option value="Angular">Angular</option>
            <option value="React">React</option>
        </select>
        <div class="submit">
            <button>Create an Account</button>
        </div>
    </form>
    <form style="background: black; color: white">
        <p id="Name"></p>
        <p id="Surname"></p>
        <p id="Age"></p>
        <p id="Email"></p>
        <p id="FF"></p>
    </form>
  </template>
  
  <script>
  
  export default {
    data() {
      return {
        Formdata:{
            name: "Иван",
            surname: "Иванов",
            age: "26",
            email: "Ivam@mail.ru",
            FF: "Vue",   
        },
        SendedData:{
            name: "",
            surname: "",
            age: "",
            email: "",
            FF: "",
        }
      }
    },
    methods:{
        SignUp(){
            let count = 0;
            if(this.Formdata.name =="") count++;
            if(this.Formdata.surname =="") count++;
            if(this.Formdata.age == "") count++;
            if(this.Formdata.email == "") count++;
            if(this.Formdata.FF == "") count++;
            if(count == 0){
                this.showInfo()
            }else{
                alert("Fill in all the fields!");
            }
        },
        showInfo() {

            this.SendedData.name = this.Formdata.name
            this.SendedData.surname = this.Formdata.surname
            this.SendedData.age = this.Formdata.age
            this.SendedData.email = this.Formdata.email
            this.SendedData.FF = this.Formdata.FF

            this.Formdata.name =""
            this.Formdata.surname =""
            this.Formdata.age =""
            this.Formdata.email =""
            this.Formdata.FF =""

            const name = document.getElementById("Name");
            const surname = document.getElementById("Surname");
            const age = document.getElementById("Age");
            const email = document.getElementById("Email");
            const FF = document.getElementById("FF");
            name.innerHTML = `{ Name: ${this.SendedData.name} }`;
            surname.innerHTML = `{ Surname: ${this.SendedData.surname} }`;
            age.innerHTML = `{ Age: ${this.SendedData.age} }`;
            email.innerHTML = `{ Email: ${this.SendedData.email} }`;
            FF.innerHTML = `{ Favorite Framework: ${this.SendedData.FF} }`;
        }
    }
  }
  
  
  </script>
  
  <style>
  form{
    max-width: 420px;
    margin: 30px auto;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
  }
  
  label{
    color:#aaaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 10px;
    font-weight: bold;
    text-transform: uppercase;
    border: none;
    letter-spacing: 1px;
    font-weight: bold;
  }
  input, select{
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
  }
  
  button{
    background-color: #0b6dff;
    border: 0;
    padding: 10px 20px;
    margin-top: 20px;
    color: white;
    border-radius: 20px;
  }
  .submit {
    text-align: center;
  }
  </style>
  
