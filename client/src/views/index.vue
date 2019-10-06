<template>
  <div>
    <header class="header-section">
      <div class="container">
        <!-- logo -->
        <a class="site-logo" href="index.html">
          <!-- <img src="../assets/img/home/img/logo.png" alt=""> -->
        </a>
        <div class="user-panel">
          <a href="/login">Login</a> /  <a href="/register">Register</a>
        </div>
        <!-- responsive -->
        <div class="nav-switch">
          <i class="fa fa-bars" />
        </div>
        <!-- site menu -->
        <nav class="main-menu">
          <ul>
            <li><a href="#basicModule">Basic Module</a></li>
            <li><a href="#subsystem">Subsystem</a></li>

          </ul>
        </nav>
      </div>
    </header>
  </div>
</template>

<script>
var loadScript = function() {
  document.write(unescape("%3Cscript src='../assets/js/jquery-3.2.1.min.js' type='text/javascript'%3E%3C/script%3E")) // Load the Local file (if google is down for some reason)
  document.write(unescape("%3Cscript src='../assets/js/bootstrap.min.js' type='text/javascript'%3E%3C/script%3E"))
  document.write(unescape("%3Cscript src='../assets/js/owl.carousel.min.js' type='text/javascript'%3E%3C/script%3E"))
  document.write(unescape("%3Cscript src='../assets/js/jquery.marquee.min.js' type='text/javascript'%3E%3C/script%3E"))
  document.write(unescape("%3Cscript src='../assets/js/main.js' type='text/javascript'%3E%3C/script%3E"))
}

export default {
  data() {
    return {
      timestamp: ''
    }
  },
  metaInfo() {
    return {
      link: [
        {
          once: true,
          rel: 'stylesheet',
          href: '../assets/css/bootstrap.min.css'
        },
        {
          once: true,
          rel: 'stylesheet',
          href: '../assets/css/font-awesome.min.css'
        },
        {
          once: true,
          rel: 'stylesheet',
          href: '../assets/css/owl.carousel.css'
        },
        {
          once: true,
          rel: 'stylesheet',
          href: '../assets/css/style.css'
        },
        {
          once: true,
          rel: 'stylesheet',
          href: '../assets/css/animate.css'
        }
      ]
    }
  },
  mounted: function() {
    this.$nextTick(function() {
      loadScript()
    })
  },
  created() {
    setInterval(this.getNow, 1000)
    this.loadScript
  },
  methods: {
    loadScript: function() {
      document.write(unescape("%3Cscript src='../assets/js/jquery-3.2.1.min.js' type='text/javascript'%3E%3C/script%3E")) // Load the Local file (if google is down for some reason)
      document.write(unescape("%3Cscript src='../assets/js/bootstrap.min.js' type='text/javascript'%3E%3C/script%3E"))
      document.write(unescape("%3Cscript src='../assets/js/owl.carousel.min.js' type='text/javascript'%3E%3C/script%3E"))
      document.write(unescape("%3Cscript src='../assets/js/jquery.marquee.min.js' type='text/javascript'%3E%3C/script%3E"))
      document.write(unescape("%3Cscript src='../assets/js/main.js' type='text/javascript'%3E%3C/script%3E"))
    },
    getNow: function() {
      const today = new Date()
      const date = today.getFullYear()
      this.timestamp = date
    }
  }
}

</script>
