<template>
  <div class="wrapper">
    <nav class="nav">
      <div class="nav-logo">
        <p>vikkywise login</p>
      </div>
      <div class="nav-menu" :class="{ responsive: isMenuOpen }" id="navMenu">
        <ul>
          <li><a href="#" class="link active">Home</a></li>
          <li><a href="#" class="link">Blog</a></li>
          <li><a href="#" class="link">Services</a></li>
          <li><a href="#" class="link">About</a></li>
        </ul>
      </div>
      <div class="nav-button">
        <button class="btn white-btn" :class="{ 'white-btn': isLoginActive }" @click="showLogin">Sign In</button>
        <button class="btn" :class="{ 'white-btn': !isLoginActive }" @click="showRegister">Sign Up</button>
      </div>
      <div class="nav-menu-btn">
        <i class="bx bx-menu" @click="toggleMenu"></i>
      </div>
    </nav>

    <div class="form-box">
      <div class="login-container" id="login" :style="{ left: loginPosition }">
        <div class="top">
          <span>Don't have an account? <a href="#" @click.prevent="showRegister">Sign Up</a></span>
          <header>Login</header>
        </div>
        <div class="input-box">
          <input type="text" class="input-field" placeholder="Username or Email">
          <i class="bx bx-user"></i>
        </div>
        <div class="input-box">
          <input type="password" class="input-field" placeholder="Password">
          <i class="bx bx-lock-alt"></i>
        </div>
        <div class="input-box">
          <input type="submit" class="submit" value="Sign In">
        </div>
        <div class="two-col">
          <div class="one">
            <input type="checkbox" id="login-check">
            <label for="login-check"> Remember Me</label>
          </div>
          <div class="two">
            <label><a href="#">Forgot password?</a></label>
          </div>
        </div>
      </div>

      <div class="register-container" id="register" :style="{ right: registerPosition }">
        <div class="top">
          <span>Have an account? <a href="#" @click.prevent="showLogin">Login</a></span>
          <header>Sign Up</header>
        </div>
        <div class="two-forms">
          <div class="input-box">
            <input type="text" class="input-field" placeholder="Firstname">
            <i class="bx bx-user"></i>
          </div>
          <div class="input-box">
            <input type="text" class="input-field" placeholder="Lastname">
            <i class="bx bx-user"></i>
          </div>
        </div>
        <div class="input-box">
          <input type="text" class="input-field" placeholder="Email">
          <i class="bx bx-envelope"></i>
        </div>
        <div class="input-box">
          <input type="password" class="input-field" placeholder="Password">
          <i class="bx bx-lock-alt"></i>
        </div>
        <div class="input-box">
          <input type="submit" class="submit" value="Register">
        </div>
        <div class="two-col">
          <div class="one">
            <input type="checkbox" id="register-check">
            <label for="register-check"> Remember Me</label>
          </div>
          <div class="two">
            <label><a href="#">Terms & conditions</a></label>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false,
      isLoginActive: true,
    };
  },
  computed: {
    loginPosition() {
      return this.isLoginActive ? '4px' : '-510px';
    },
    registerPosition() {
      return this.isLoginActive ? '-520px' : '5px';
    },
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    showLogin() {
      this.isLoginActive = true;
    },
    showRegister() {
      this.isLoginActive = false;
    },
  },
};
</script>

<style scoped>


*{  
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Poppins, sans-serif;
}
template {
  
 
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: center;
}
.wrapper{
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 110vh;
    background: url('@/assets/background.jpg') no-repeat center center fixed;
     background-size: cover;
  height: 100vh;
    /* background: rgba(39, 39, 39, 0.4); */
}
.nav{
    position: fixed;
    top: 0;
    display: flex;
    justify-content: space-around;
    width: 100%;
    height: 100px;
    line-height: 100px;
    background: linear-gradient(rgba(39,39,39, 0.6), transparent);
    z-index: 100;
}
.nav-logo p{
    color: white;
    font-size: 25px;
    font-weight: 600;
}
.nav-menu ul{
    display: flex;
}
.nav-menu ul li{
    list-style-type: none;
}
.nav-menu ul li .link{
    text-decoration: none;
    font-weight: 500;
    color: #fff;
    padding-bottom: 15px;
    margin: 0 25px;
}
.link:hover, .active{
    border-bottom: 2px solid #fff;
}
.nav-button .btn{
    width: 130px;
    height: 40px;
    font-weight: 500;
    background: rgba(255, 255, 255, 0.4);
    border: none;
    border-radius: 30px;
    cursor: pointer;
    transition: .3s ease;
}
.btn:hover{
    background: rgba(255, 255, 255, 0.3);
}
#registerBtn{
    margin-left: 15px;
}
.btn.white-btn{
    background: rgba(255, 255, 255, 0.7);
}
.btn.btn.white-btn:hover{
    background: rgba(255, 255, 255, 0.5);
}
.nav-menu-btn{
    display: none;
}
.form-box{
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 512px;
    height: 420px;
    overflow: hidden;
    z-index: 2;
}
.login-container{
    position: absolute;
    left: 4px;
    width: 500px;
    display: flex;
    flex-direction: column;
    transition: .5s ease-in-out;
}
.register-container{
    position: absolute;
    right: -520px;
    width: 500px;
    display: flex;
    flex-direction: column;
    transition: .5s ease-in-out;
}
.top span{
    color: #fff;
    font-size: small;
    padding: 10px 0;
    display: flex;
    justify-content: center;
}
.top span a{
    font-weight: 500;
    color: #fff;
    margin-left: 5px;
}
header{
    color: #fff;
    font-size: 30px;
    text-align: center;
    padding: 10px 0 30px 0;
}
.two-forms{
    display: flex;
    gap: 10px;
}
.input-field{
    font-size: 15px;
    background: rgba(255, 255, 255, 0.2);
    color: #fff;
    height: 50px;
    width: 100%;
    padding: 0 10px 0 45px;
    border: none;
    border-radius: 30px;
    outline: none;
    transition: .2s ease;
}
.input-field:hover, .input-field:focus{
    background: rgba(255, 255, 255, 0.3);
}
.input-box{
    position: relative;
    width: 100%;
    height: 50px;
    margin-bottom: 20px;
}
.input-box i{
    position: absolute;
    color: #fff;
    font-size: 23px;
    top: 50%;
    transform: translateY(-50%);
    left: 15px;
}
.submit{
    font-size: 15px;
    font-weight: 600;
    color: #414141;
    width: 100%;
    height: 50px;
    border: none;
    border-radius: 30px;
    outline: none;
    cursor: pointer;
    transition: .2s ease;
}
.submit:hover{
    background: rgba(255, 255, 255, 0.8);
}
.two-col{
    display: flex;
    justify-content: space-between;
    color: #fff;
    font-size: small;
}
label a{
    color: #fff;
}
.nav-menu.responsive {position: relative;}
.nav-menu.responsive ul {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: rgba(0, 0, 0, 0.9);
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    line-height: 100px;
}
.nav-menu.responsive ul li .link{
    margin: 30px;
}
.nav-menu-btn{
    display: none;
}
@media screen and (max-width: 960px) {
    .nav-menu ul{
        display: none;
    }
    .nav-menu-btn{
        display: block;
        color: #fff;
        font-size: 30px;
        cursor: pointer;
    }
    .nav-button .btn{
        width: 110px;
        height: 40px;
        font-size: 14px;
    }
}
</style>
