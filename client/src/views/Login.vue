<template>
<div class="whole">
    <div class="main">
    <div class='container'>
        <div class='row'>
            <div class ='col-md-8'>
    <br><br>
        <h2> Login </h2>
       <form>
        <div class ='form-group text-left'>
            <label for = 'User Name'>User Name</label>
            <input type ='text' name='username' id= 'username' placeholder='Enter Username' v-model='username' class='form-control'/>
        </div>
        <div class ='form-group text-left'>
            <label for = 'Password'>Password</label>
            <input type ='password' name='pswd' id= 'pswd' placeholder='Enter Password' v-model='pswd' class='form-control'/>
        </div>
        <br>
        <div class="buton">
        <button type="submit" class="btn btn-success">Login</button> &nbsp; &nbsp;
         <button type="reset" class="btn btn-success">Reset</button>
        </div>
        </form>
        </div>
    </div>
    </div>
    </div>
    <footer id="footerlog"> 
    COPYRIGHT &copy; WEEABOO 2020 | ALL RIGHTS RESERVED.
</footer>
</div>
</template>