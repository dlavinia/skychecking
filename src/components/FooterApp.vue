<template>
    <footer>
       <nav>
            <ul>
                <li> <a href="https://github.com/dlavinia"><img src="https://raw.githubusercontent.com/dlavinia/feliznatal/1730a7fd4a3bb7c0edca1c9e7c0b4b3c5c11419a/src/assets/github.svg" title="GitHub" alt="GitHub"></a></li>
                <li> <a href="https://www.linkedin.com/in/d%C3%A9bora-melo-8b03aa205/"><img src="https://raw.githubusercontent.com/dlavinia/feliznatal/1730a7fd4a3bb7c0edca1c9e7c0b4b3c5c11419a/src/assets/linkedin.svg" title="Linkedin" alt="=LinkedIn"></a></li>
                <li> <a href="emailto:dlavinia2003@gmail.com"><img src="https://raw.githubusercontent.com/dlavinia/feliznatal/1730a7fd4a3bb7c0edca1c9e7c0b4b3c5c11419a/src/assets/gmail.svg" title="Email" alt="Email"></a></li>
            </ul>
       </nav>
    </footer>
  </template>
  
  <script>
  export default {
    name: 'FooterPage',
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
    footer{
        background-color: #fff;
        display: flex;
        justify-content: center;
        align-items: center;
        padding:3rem 5rem;
    }
    nav{
        width: 18%;
    }
    ul{
        display: flex;
        justify-content: space-around;
        list-style: none;
    }
    img{
        width: 54px;
    }
    a{
        padding: 8px;
        font-size: 22px;
        font-weight: 500;
        color: var(--dark-color-text);
    }
    @media only screen and (max-width: 600px) {
        nav{ width: 100%;}
    }
  </style>