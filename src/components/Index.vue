<template>
<div class="page">
    <div class="header-logo">
        <p class="header-title">INDIABIZ</p>
    </div>
    <div class="dashboard">
        <div class="container">
            <div class="dashboard-container">
                <p class="dashboard-context align">You are with the most preferred business network to buy,sell,fund,grow</p>
                <form >
                  <div class="radio radio-info">
                      <input type="radio" id="preferred1" v-validate="'required|in:1,2'" value="1" name="preferred" >
                       <label for="preferred1">I am an Individual
                    </label>
                    </div>
                  <div class="radio radio-info sec-button">
                      <input type="radio" id= "preferred2" value="2" name="preferred">
                       <label for="preferred2">I own or represent a business
                    </label>
                  </div>
            <span class="alert-errors align is-danger" v-show="errors.has('preferred')">{{ errors.first('preferred') }}</span>
                    <button type="button" class="btn primary-button" v-on:click="validateForm">Continue</button>
                </form>
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
</div>
    </template>
    <script>
    import Vue from 'vue'
    import VeeValidate from 'vee-validate'
    Vue.use(VeeValidate)
    export default {
    name: 'radio-buttons-example',
    data: () => ({
    preferred: ''
    }),
    methods: {
    validateForm () {
    this.$validator.validateAll().then((result) => {
    if (result) {
    alert('All Passes!')
    return
    }
    alert('Oh NO!')

    })
    }
    }
    }
    </script>
    <style>
    html, body {
    width: 100%;
    height: 100%;
    margin: 0 !important;
    padding: 0 !important;
    background-color: #f7f7f7;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;

    }
    .page{
    height:auto;
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
    }
    p.header-title {
    margin-top: 0;
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
    margin-left:36%;
    width:33%;
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
        margin-left:30px;
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
    }
    .radio{
        margin-left: 30px;
    }

    .radio label {
    display: inline-block;
    position: relative;
    padding-left: 5px; 
margin-bottom: 4px}
    .radio label::before {
    content: "";
    display: inline-block;
    position: absolute;
    width: 17px;
    height: 16px;
    left: 0;
    margin-left: -21px;
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

    @media screen and (min-width: 320px) and (max-width: 500px) {
        .dashboard-container{
            
    padding:30px 0;
    margin-left:25%;
    width:50%;
    text-align:left;
        }
        .dashboard-context{
    font-size:15px;
    font-weight:600;
    margin-bottom: 30px;
    }
    .footer{
        margin-left:-45px;
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
    margin-left:30px;
    width:42%;
    height: 36px;
    border:0;
    border-radius:3px;
    background-color:#3497DB;
    color:#fff;
    font-size: 12px !important;
    font-weight: 600 !important;
    margin-top:5%;
    }
    .radio{
        margin-left: 30px !important;
    }
    .sec-button{
        margin-left:55px !important;
    }
}

 @media screen and (min-width: 501px) and (max-width: 703px) {
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
    margin-left:30px;
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

@media screen and (min-width: 704px) and (max-width: 839px) {
         .dashboard-container{
    padding:30px 0;
    margin-left:20%;
    width:70%;
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
    margin-left:30px;
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