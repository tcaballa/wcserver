<template>
<div class="wholesign">
    <div class='container'>
        <div class='row'>
            <div class ='col-md-8'>
    <br><br>
        <h2> Create an Account. </h2>
       <form @submit.prevent = 'registerUser'>
            <div class ='form-group text-left'>
            <label for = 'First Name'>First Name</label>
            <input type ='text' name='fname' id= 'fname' placeholder='Enter First Name' v-model='fname' class='form-control'/>
            <p id ="required_fname">{{fname_validation}}</p>
        </div>
        <div class ='form-group text-left'>
            <label for = 'midInitial'>Middle Initial</label>
            <input type ='text' name='mi' id= 'mi' placeholder='Enter Middle Initial' v-model='mi' class='form-control'/>
        </div>
        <div class ='form-group text-left'>
            <label for = 'Last Name'>Last Name</label>
            <input type ='text' name='lname' id= 'lname' placeholder='Enter Last Name' v-model='lname' class='form-control'/>
            <p id ="required_lname">{{lname_validation}}</p>
        </div>
        <div class ='form-group text-left'>
            <label for = 'Address'>Address</label>
            <input type ='text' name='address' id= 'address' placeholder='Enter Address' v-model='address' class='form-control'/>
            <p id ="required_address">{{address_validation}}</p>
        </div>
        <div class ='form-group text-left'>
            <label for = 'Date of Birth'>Date of Birth</label>
            <input type ='date' name='bday' id= 'bday' placeholder='Enter Date of Birth' v-model='bday' class='form-control'/>
            <p id ="required_bday">{{bday_validation}}</p>
        </div>
        <div class ='form-group text-left'>
            <label for = 'Contact No'>Contact </label>
            <input type ='text' name='contact' id= 'contact' placeholder='Enter Contact No' v-model='contact' class='form-control'/>
            <p id ="required_contact">{{contact_validation}}</p>
        </div>
        <div class ='form-group text-left'>
            <label for = 'Email'>Email Address</label>
            <input type ='text' name='email' id= 'email' placeholder='Enter Email Address' v-model='email' class='form-control'/>
            <p id ="required_email">{{email_validation}}</p>
        </div>
        <div class ='form-group text-left'>
            <label for = 'User Name'>User Name</label>
            <input type ='text' name='username' id= 'username' placeholder='Enter Username' v-model='username' class='form-control'/>
            <p id ="required_username">{{username_validation}}</p>
        </div>
        <div class ='form-group text-left'>
            <label for = 'Password'>Password</label>
            <input type ='password' name='pswd' id= 'pswd' placeholder='Enter Password' v-model='pswd' class='form-control'/>
            <p id ="required_pswd">{{pswd_validation}}</p>
        </div>
        <br>
        <div class="buton">
        <button type="submit" class="btn btn-success">Sign Up</button> &nbsp; &nbsp;
         <button type="reset" class="btn btn-success">Reset</button>
        </div>
             <br><br>
        </form>
        </div>
    </div>
    </div>
<footer id="footer"> 
    COPYRIGHT &copy; WEEABOO 2020 | ALL RIGHTS RESERVED.
</footer>
</div>
</template>

<script>
import axios from 'axios'
// import touter from '../router'
export default {
    data () {
        return  {
            fname: '',
            mi: '',
            lname: '',
            address: '',
            bday: '',
            contact: '',
            email: '',
            username: '',
            pswd: '',
            fname_validation: '',
            lname_validation: '',
            address_validation: '',
            bday_validation: '',
            contact_validation: '',
            email_validation: '',
            username_validation: '',
            pswd_validation: '',
        }
    },
    methods: {
        registerUser() {
            if (this.fname === '') {
               // alert('Please enter your First Name: ')
               this.fname_validation = 'Please enter your first name. '
            }
            else if (this.lname === '') {
                this.lname_validation = 'Please enter your last name. '
            }
            else if (this.address === '') {
                this.address_validation = 'Please enter your address. '
            }
            else if (this.bday === '') {
                this.bday_validation = 'Please enter your date of birth. '
            }
            else if (this.contact === '') {
                this.contact_validation = 'Please enter your contact number. '
            }
            else if (this.email === '') {
                this.email_validation = 'Please enter your email address. '
            }
            else if (this.username === '') {
                this.username_validation = 'Please enter your username. '
            }
            else if (this.pswd === '') {
                this.pswd_validation = 'Please enter your password. '
            }
            else {
                this.createUser()
             }
        },
        createUser() {
            axios.post('users/register', {
                first_name: this.fname,
                middle_initial: this.mi,
                last_name: this.lname,
                address: this.address,
                birthday: this.bday,
                contact_no: this.contact,
                email_address: this.email,
                username: this.username,
                password: this.pswd

            })
        }
    }
}
</script>

<style>
#required_fname, #required_lname, #required_address, #required_bday, #required_contact, #required_email, #required_username, #required_pswd {
    color: red;
}
</style>