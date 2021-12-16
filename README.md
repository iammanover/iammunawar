<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>login form</title>
    <link rel="stylesheet" href="style.css" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,500;0,900;1,100&display=swap"
      rel="stylesheet"
    />

    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.15.4/css/all.css"
      integrity="sha384-DyZ88mC6Up2uqS4h/KRgHuoeGwBcD4Ng9SiP4dIRy0EXTlnuz47vAwmeGwVChigm"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <div class="container">
      <div class="title">LogIn Form</div>
      <div class="content">
        <form action="#" name="forms" id="forms" onsubmit="return validation()">
          <div class="user-details">
            <div class="input-box">
              <span class="details">First Name</span>
              <input type="text" id="name" placeholder="Enter your name" />
              <span class="error" id="Fname" style="color: red"></span>
            </div>
            <div class="input-box">
              <span class="details">Last Name</span>
              <input
                type="text"
                id="lname"
                placeholder="Enter your name"
              /><span class="error" id="Lname" style="color: red"></span>
            </div>
            <div class="input-box">
              <span class="details">Username</span>
              <input
                type="text"
                id="user"
                placeholder="Enter your username"
              /><span class="error" id="username" style="color: red"></span>
            </div>
            <div class="input-box">
              <span class="details">Email</span>
              <input
                type="text"
                id="email"
                placeholder="Enter your email"
              /><span class="error" id="mail" style="color: red"></span>
            </div>
            <div class="input-box">
              <span class="details">Phone Number</span>
              <input
                type="tel"
                id="phone"
                placeholder="Enter your number"
                maxlength="10"
              /><span class="error" id="contact" style="color: red"></span>
            </div>
            <div class="input-box">
              <span class="details">Password</span>
              <input
                type="password"
                id="password"
                placeholder="Enter your password"
              /><span class="error" id="pass" style="color: red"></span>
            </div>
            <div class="input-box">
              <span class="details">Address</span>
              <textarea
                name="address"
                id="address"
                cols="80"
                rows="5"
                placeholder="Enter your full Address"
              ></textarea
              ><span class="error" id="add" style="color: red"></span>
            </div>
          </div>
          <!-- Gender -->
          <div class="gender-details">
            <input type="radio" name="gender" id="dot-1" />
            <input type="radio" name="gender" id="dot-2" />
            <input type="radio" name="gender" id="dot-3" />
            <span class="gender-title" id="gender">Gender</span><br />
            <span class="error" id="gen" style="color: red"></span>
            <div class="category">
              <label for="dot-1">
                <span class="dot one"></span>
                <span class="gender">Male</span>
              </label>
              <label for="dot-2">
                <span class="dot two"></span>
                <span class="gender">Female</span>
              </label>
              <label for="dot-3">
                <span class="dot three"></span>
                <span class="gender">Others</span>
              </label>
            </div>
          </div>
          <!-- Qualifications -->
          <span class="stitle" id="Qualifications">Qualifications </span
          ><span class="error" id="qua" style="color: red"></span>
          <div class="qualifications">
            <label for="SSC">
              <span class="SSC">SSC</span>
              <input type="checkbox" name="Qualifications" id="SSC" /></label
            >
            <label for="HSC">
              <span class="HSC">HSC</span>
              <input type="checkbox" name="Qualifications" id="HSC"
            /></label>
            <label for="BCA">
              <span class="BCA">BCA</span>
              <input type="checkbox" name="Qualifications" id="BCA"
            /></label>
            <label for="MCA">
              <span class="MCA">MCA</span>
              <input type="checkbox" name="Qualifications" id="MCA"
            /></label>
            <label for="PHD">
              <span class="PHD">PHD</span>
              <input type="checkbox" name="Qualifications" id="PHD"
            /></label>
          </div>
          <div class="button">
            <input type="submit" value="LogIn" name="submit" />
          </div>
        </form>
      </div>
    </div>
    <!--  type="text/javascript" -->

    <script type="text/javascript">

      
      function validation() {
        // First NAME VALIDATION
        var Fname = document.getElementById("name").value;

        if (Fname == "") {
          document.getElementById("Fname").innerHTML =
            "* please enter your name";
          return false;
        } else if (!isNaN(Fname)) {
          document.getElementById("Fname").innerHTML =
            "*numbers are not allowed";
          return false;
        } else {
           //document.getElementById("Fname").innerHTML = "";
           
        }

        // Username
        var user = document.getElementById("user").value;

        if (user == "") {
          document.getElementById("username").innerHTML =
            "* please enter your username";
          return false;
        } else if (user.length <= 2) {
          document.getElementById("username").innerHTML =
            "* user length must be between 2 and 20";
          return false;
        } else if (user.length > 20) {
          document.getElementById("username").innerHTML =
            "* user length must be between 2 and 20";
          return false;
        } else {
          document.getElementById("username").innerHTML = "";
        }


        // email
        var email = document.getElementById("email").value;
        var who = /^[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,4}$/;
        if (email == "") {
          document.getElementById("mail").innerHTML =
            "* please enter your mail id";
          return false;
        } else {
          document.getElementById("mail").innerHTML = "";
        }

        if (who.test(email)) {
          document.getElementById("mail").innerHTML = "";
        } else {
          document.getElementById("mail").innerHTML =
            " please enter valid emial id ";
          return false;
        }

        //phone
        var phone = document.getElementById("phone").value;
        var phoneRegex = /^[7869][0-9]{9}$/;

        if (phone == "") {
          document.getElementById("contact").innerHTML =
            "* please enter your contact number";
          return false;
        } else {
          document.getElementById("contact").innerHTML = "";
        }

        if (phoneRegex.test(phone)) {
          document.getElementById("contact").innerHTML = "";
        } else {
          document.getElementById("contact").innerHTML =
            "* invalid phone number";
          return false;
        }

        if (isNaN(phone)) {
          document.getElementById("contact").innerHTML =
            "*This is not a phone number";
          return false;
        } else {
          document.getElementById("contact").innerHTML = "";
        }

        if (phone.length != 10) {
          document.getElementById("contact").innerHTML =
            "*Phone number must have 10 digits";
          return false;
        } else {
          document.getElementById("contact").innerHTML = "";
        }

        //password
        var password = document.getElementById("password").value;

        if (password == "") {
          document.getElementById("pass").innerHTML = "* please enter password";
          return false;
        } else if (password.length <= 5) {
          document.getElementById("pass").innerHTML =
            "* password length must be between 5 and 20";
          return false;
        } else if (password.length > 20) {
          document.getElementById("pass").innerHTML =
            "* password length must be between 5 and 20";
          return false;
        } else {
          document.getElementById("pass").innerHTML = "";
        }

        //address
        var address = document.getElementById("address").value;

        if (address == "") {
          document.getElementById("add").innerHTML =
            "* please enter your address";
          return false;
        } else {
          document.getElementById("add").innerHTML = "";
        }

        // Gender
        var gender = document.forms.gender;

        for (i = 0; i < gender.length; i++) {
          if (gender[i].checked == true) return true;
          else {
            document.getElementById("gen").innerHTML = "";
          }
        }

        document.getElementById("gen").innerHTML =
          " *Please select your gender";
        return false;

        //  Qualifications

        var Qualifications = document.forms.Qualifications.value;

        // for (i = 0; i < Qualifications.length; i++) {
        //   if (Qualifications[i].checked == true) return true;
        //   else {
        //     document.getElementById("qua").innerHTML = "";
        //   }
        // }
        // document.getElementById("qua").innerHTML =
        //   "* please check anyone Qualifications";
        // return false;
        if (Qualifications.length == 0) {
          document.getElementById("qua").innerHTML =
         "* please check anyone Qualifications";
         return false;
        }else{
          document.getElementById("qua").innerHTML = "";
        }
        
      }
    </script>
  </body>
</html>
