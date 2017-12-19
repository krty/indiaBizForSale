<template>
<div class="page">
    <div class="header-logo">
        <p class="header-title">INDIABIZ</p>
    </div>
    <div class="dashboard">
        <div class="container">
            <div class="dashboard-container">
                <p class="dashboard-context align"> Sign Up</p>
                <div id="app">
                       <form >
    
    <div class="column  align">
        <label class="label">Name</label>
        <p class="control has-icon has-icon-right">
            <input name="name" v-model="name" v-validate="'required|alpha'" :class="{'input': true, 'is-danger': errors.has('name') }" type="text" placeholder="Name">
            <i v-show="errors.has('name')" class="fa fa-warning"></i>
            <span v-show="errors.has('name')" class="alert-errors  help is-danger">{{ errors.first('name') }}</span>
        </p>
    </div>
    <div class="column  align">
        <label class="label">Email</label>
        <p class="control has-icon has-icon-right">
            <input name="email" v-model="email" v-validate="'required|email'" :class="{'input': true, 'is-danger': errors.has('email') }" type="text" placeholder="Email">
            <i v-show="errors.has('email')" class="fa fa-warning"></i>
            <span v-show="errors.has('email')" class="alert-errors  help is-danger">{{ errors.first('email') }}</span>
        </p>
    </div>
    <div class="column  align">
        <label class="label">Create a Password</label>
        <p class="control has-icon has-icon-right">
            <input name="password" v-model="password" v-validate="'required|min:6|max:10'" :class="{'input': true, 'is-danger': errors.has('password') }" type="password" placeholder="Password">
            <i v-show="errors.has('password')" class="fa fa-warning"></i>
            <span v-show="errors.has('password')" class="alert-errors  help is-danger">{{ errors.first('password') }}</span>
        </p>
    </div>
<div class="column  align">
        <p class="terms">By clicking the button,you agreeing to our <a href="#">terms & conditions</a></p>
        </div>
    <div class="column  align">
        <p class="control">
            <button class="button primary-button" type="submit" v-on:click="signUp">SignUp</button>
        </p>
    </div>
</form>
                </div>
            </div>
            
        </div>
        <div class="footer">
            <ul class="footer-container">
                <li><span class="glyphicon glyphicon-copyright-mark">2018 Indiabizforsale</span></li>
                <li><a href="#">Terms</a> </li>
                <li><a href="#">Privacy</a> </li>
                <li><a href="#">Contact Us</a> </li>
            </ul>
        </div>
    </div>
    
</div>
</template>

<script>
import Vue from 'vue'
import VeeValidate from 'vee-validate'
import axios from 'axios'

Vue.use(VeeValidate)
Vue.use(axios)
export default {
  name: 'form-example',
  data: () => ({
    email: '',
    name: '',
    phone: '',
    url: ''
  }),
  methods: {
     signUp (e) {
        this.$validator.validateAll().then((result) => {
          if (result) {
            console.log(this.data);
           axios.post(`https://demo3235314.mockable.io`, {
            body: this.data
          }).then(response => {
            console.log(this.data);
            console.log(response);
            if(response.status === 201)
            {
              alert("signed up successfully");
            }
          }).catch(e => {this.errors.push(e)
          })

          }
        })
      }
  }
}
</script>
<style>
html, body {
width: 100%;
height: 100%;
margin: 0;
padding: 0;
background-color: #f7f7f7;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;

}
.page{
height:auto;
}
p.header-title {
    margin-top: 0;
}
.header-logo
{
height: 10%;
background-color: #2C3D4F;
color:#fff;
}
.header-title
{
font-size: 20px;
padding-left: 25px;
padding-top:30px;
padding-bottom:10px;
}
.dashboard
{
width:100%;
height:600px;
background-color: #f7f7f7;
}
.dashboard-container{
margin-top:3%;
background-color: #fff;
height:auto;
border-radius:5px;
padding:30px 0;
 margin-left:32%;
    width:41%;
    text-align:left;
}
.dashboard-context{
font-size:21px;
font-weight:600;
margin-bottom: 50px;
line-spacing:1.5px;
}
.align{
padding-left:40px;
padding-right:40px;
}
.primary-button{
width:42%;
height: 36px;
border:0;
border-radius:3px;
background-color:#3497DB;
color:#fff;
font-size: 14px !important;
font-weight: 600 !important;
margin-top:5%;
}
.icon-edit{
margin-right:41px;
color:red;
}
.alert-errors{
color:red;
}
.terms{
font-size: 14px;
}
.terms a {
text-decoration: none;
color:#3497DB;
}
.radio {
padding-left: 20px; }
.radio label {
display: inline-block;
position: relative;
padding-left: 5px; }
.radio label::before {
content: "";
display: inline-block;
position: absolute;
width: 17px;
height: 17px;
left: 0;
margin-left: -20px;
border: 1px solid #5bc0de;
border-radius: 50%;
background-color: #fff;
-webkit-transition: border 0.15s ease-in-out;
-o-transition: border 0.15s ease-in-out;
transition: border 0.15s ease-in-out; }
.radio label::after {
display: inline-block;
position: absolute;
content: " ";
width: 11px;
height: 11px;
left: 3px;
top: 3px;
margin-left: -20px;
border-radius: 50%;
background-color: #555552;
-webkit-transform: scale(0, 0);
-ms-transform: scale(0, 0);
-o-transform: scale(0, 0);
transform: scale(0, 0);
-webkit-transition: -webkit-transform 0.1s cubic-bezier(0.8, -0.33, 0.2, 1.33);
-moz-transition: -moz-transform 0.1s cubic-bezier(0.8, -0.33, 0.2, 1.33);
-o-transition: -o-transform 0.1s cubic-bezier(0.8, -0.33, 0.2, 1.33);
transition: transform 0.1s cubic-bezier(0.8, -0.33, 0.2, 1.33); }
.radio input[type="radio"] {
opacity: 0; }
.radio input[type="radio"]:focus + label::before {
outline: thin dotted;
outline: 5px auto -webkit-focus-ring-color;
outline-offset: -2px; }
.radio input[type="radio"]:checked + label::after {
-webkit-transform: scale(1, 1);
-ms-transform: scale(1, 1);
-o-transform: scale(1, 1);
transform: scale(1, 1); }
.radio input[type="radio"]:disabled + label {
opacity: 0.65; }
.radio input[type="radio"]:disabled + label::before {
cursor: not-allowed; }
.radio.radio-inline {
margin-top: 0; }
.
.radio-info input[type="radio"] + label::after {
background-color: #5bc0de; }
.radio-info input[type="radio"]:checked + label::before {
border-color: #5bc0de; }
.radio-info input[type="radio"]:checked + label::after {
background-color: #5bc0de; }
.footer{
background-color: #f7f7f7;
/*top:500px;*/
/*left:-364px;*/
text-align: center;
margin-top: 2%;
}
.footer ul li{
display: inline;
margin-right:5px;
margin-left:5px;
font-size: 12px;
}
.footer ul li a {
text-decoration: none;
}
input[type="text"]{
        width: 100%;
    height: 27px;
    font-size: 16px;
    margin-bottom:3px;
}input[type="password"]{
        width: 100%;
    height: 27px;
    font-size: 16px;
    margin-bottom:3px;
}

@media only screen (max-width:767px) {
     .dashboard-container{
            
    padding:30px 0;
    margin-left:25%;
    width:60%;
    text-align:left;
        }
        .dashboard-context{
    font-size:15px;
    font-weight:600;
    margin-bottom: 30px;
    }
    .footer{
        margin-left:-20px;
    }
    .footer ul li{
        margin-right:1px;
    margin-left:1px;
    font-size: 10px;
    }
.radio label{
    font-size:12px;
}
.alert-errors{
    font-size: 12px;
}
 .primary-button{
    margin-left:0px;
    width:60%;
    height: 36px;
    border:0;
    border-radius:3px;
    background-color:#3497DB;
    color:#fff;
    font-size: 14px !important;
    font-weight: 600 !important;
    margin-top:5%;
    }
    .label{
        font-size: 14px;
    }
    }
    @media screen and (min-width: 768px) and (max-width: 1024px) {
     .dashboard-container{
    padding:30px 0;
    margin-left:25%;
    width:58%;
    text-align:left;
        }
        .dashboard-context{
    font-size:18px;
    font-weight:600;
    margin-bottom: 30px;
 }
 .radio{
    margin-left:30px;
 }
 .primary-button{
    margin-left:0px;
    width:42%;
height: 36px;
border:0;
border-radius:3px;
background-color:#3497DB;
color:#fff;
font-size: 14px !important;
font-weight: 600 !important;
margin-top:5%;
    }
}




</style>