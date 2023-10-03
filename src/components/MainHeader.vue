<template>
    <header id="main-header" :class="['header', { 'fixed-header': fixedHeader }]">
        <div class="container">
            <div class="header-main-content d-flex justify-content-between align-items-center flex-wrap">
                <div class="logo">
                    <a class="navbar-brand" href="index.html"><img src="../static/images/logo.svg" width="105" height="24" alt="logo"></a>
                </div>
                <div class="main-navigation">
                    <div class="navbar navbar-expand-md py-0">
                        <button
                            class="navbar-toggler"
                            type="button"
                            data-bs-toggle="collapse"
                            data-bs-target="#mynavbar"
                            aria-controls="mynavbar"
                            aria-expanded="false"
                            aria-label="Toggle navigation"
                            @click="toggleNavbar"
                            :class="{ 'collapsed': !isNavbarOpen }" 
                        >
                        <span class="navbar-toggler-icon"></span>
                        </button>
                        <div class="collapse navbar-collapse" id="mynavbar" :class="{ 'show': isNavbarOpen }">
                            <button type="button" class="btn-close d-block d-md-none" @click="closeNavbar"></button>
                            <div class="navbar-logo mb-1 d-block d-md-none">
                                <img src="../static/images/logo.svg" width="140" height="48" alt="logo">
                            </div>
                            <ul class="navbar-nav me-auto">
                                <li class="nav-item">
                                    <a href="javascript:void(0);" class="nav-link" target="_blank">
                                        Twitter
                                    </a>
                                </li>
                                <li class="nav-item">
                                    <a href="javascript:void(0);" class="nav-link" target="_blank">
                                        Discord
                                    </a>
                                </li>
                                <li class="nav-item">
                                    <a href="javascript:void(0);" class="nav-link" target="_blank">
                                        Telegram
                                    </a>
                                </li>
                                <li class="nav-item">
                                    <a href="javascript:void(0);" class="nav-link" target="_blank">
                                        Document
                                    </a>
                                </li>
                                <li class="nav-item btn-link">
                                    <a href="javascript:void(0);" class="nav-link" target="_blank">
                                        Launch APP
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
export default {
  data() {
    return {
      fixedHeader: false,
      isNavbarOpen: false, // Track the state of the navbar
    };
  },
  mounted() {
    window.addEventListener('scroll', this.setFixedHeader);
  },
  methods: {
    setFixedHeader() {
      this.fixedHeader = window.pageYOffset > 10;
    },
    toggleNavbar() {
      this.isNavbarOpen = !this.isNavbarOpen;
    },
    closeNavbar() {
      this.isNavbarOpen = false;
    },
  },
};
</script>
<style lang="scss" scoped>
    header{
        padding: 0.15rem 0;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        z-index: 99;
        transition: all 0.5s ease 0s;
        &.fixed-header{
            background: rgba(255,255,255,0.9);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
        }
        @media(max-width: 767px){
            padding: 20px 0;
        }
        .logo{
            width: 1.05rem;
            img{
                height: auto;
                width: 100%;
            }
            .navbar-brand{
                height: 100%;
                display: inline-block;
            }
            @media(max-width: 767px){
                width: 80px;
            }
        }
        .main-navigation{
            font-family: var(--inter-font);
            font-weight: 500;
            .nav-link{
                padding: 0.1rem 0.15rem;
                font-size: 0.16rem;
                color: var(--black-color);
                &:hover{
                    color: var(--blue-color);
                }
                @media(max-width: 1199px){
                    font-size: 0.18rem;
                }
                @media(max-width: 767px){
                    font-size: 16px;
                    font-weight: 400;
                    padding: 7px;
                }
            }
            .nav-item.btn-link{
                margin-left: 0.22rem;
                .nav-link{
                    color: var(--white-color);
                    padding: 0.12rem 0.2rem;
                }
                @media(max-width: 767px){
                    margin-left: 0;
                    .nav-link{
                        background: none;
                        color: var(--black-color);
                        padding: 7px;
                        min-width: auto;
                        &:hover,&.active{
                            color: var(--blue-color)
                        }
                    }
                }
            }
            .nav-item.active{
                .nav-link{
                    color: var(--blue-color);
                }
            }
            .nav-item.btn-link.active{
                .nav-link{
                    color: var(--white-color);
                }
            }
            @media(max-width: 767px){
                .nav-item.btn-link.active{
                    .nav-link{
                        color: var(--blue-color);
                    }
                }
            }
        }
        .navbar-toggler{
            width: 0.35rem;
            height: 0.35rem;
            padding: 0;
            border: none;
            span{
                width: 0.35rem;
                height: 0.35rem;
                vertical-align: top;
                background-image: url('../static/images/icons/toggle-icon-active.png');
                background-size: 0.22rem;
                opacity: 1;
            }
            &:focus{
                box-shadow: none;
                opacity: 1;
            }
            &.collapsed{
                span{
                    background-image: url('../static/images/icons/toggle-icon.png');
                }
            }
            @media(max-width: 480px){
                span{
                    background-size: 17px;
                }
            }
        }
        .navbar-collapse,.navbar-collapse.collapsing{
            @media(max-width: 767px){
                left: -102%;
                height: 100vh;
                position: fixed;
                background: linear-gradient(130deg,#fff,#d8fdf8);
                padding: 30px 20px;
                top: 0;
                width: 280px;
                display: block;
                transition: all 0.4s ease 0s;
                box-shadow: 0 0 3px rgba(0,0,0,0.1);
            }
            &.show{
                left: 1px;
            }
        }
        .btn-close{
            position: absolute;
            right: 7px;
            top: 7px;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 1;
            background-size: 13px;
            &:focus{
                box-shadow: none;
            }
        }
        .navbar-logo{
            padding-left: 7px;
            padding-right: 7px;
            img{
                width: 90px;
            }
        }
    }
</style>
