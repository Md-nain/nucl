<template>
    <footer class="footer">
        <div class="container">
            <div class="d-flex flex-wrap justify-content-md-between align-items-center">
                <div class="left-content col-12 col-md-4 d-flex align-items-center justify-content-center justify-content-md-start">
                    <div class="footer-logo">
                        <img src="../static/images/footer-logo.svg" alt="logo">
                    </div>
                    <div class="copyright">
                        <span>@ 2023 NUCL Protocol, LLC.</span>
                    </div>
                </div>
                <div class="right-content col-12 col-md-8">
                    <ul class="footer-navigation list-group-flush d-flex align-items-center justify-content-center justify-content-md-end">
                        <li class="list-group-item">
                            <a href="javascript:void(0);" target="_blank">Twitter</a>
                        </li>
                        <li class="list-group-item">
                            <a href="javascript:void(0);" target="_blank">Discord</a>
                        </li>
                        <li class="list-group-item">
                            <a href="javascript:void(0);" target="_blank">Telegram</a>
                        </li>
                        <li class="list-group-item">
                            <a href="javascript:void(0);" target="_blank">Document</a>
                        </li>
                        <li class="list-group-item">
                            <a href="javascript:void(0);" target="_blank">Contact</a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>

    </footer>
</template>

<script>
export default {
    data() {
        return {};
    },
    mounted() {},
    methods: {},
};
</script>

<style lang="scss" scoped>
footer{
    padding: 0.35rem 0 0.6rem;
    .footer-logo{
        img{
            max-width: 0.24rem;
        }
    }
    .copyright{
        padding-top: 0.05rem;
        padding-left: 0.45rem;
        @media(max-width: 767px){
            padding-left: 10px;
            padding-top: 9px;
        }
    }
    .footer-navigation{
        @media(max-width: 767px){
            padding-top: 10px;
        }
        li{
            a{
                padding: 0.1rem;
                display: inline-block;
                vertical-align: top;
                font-family: var(--roboto-font);
                color: #475569;
            }
            &:hover{
                a{
                    color: var(--blue-color)
                }
            }
        }
    }
    @media(max-width: 1199px){
        font-size: 0.18rem;
    }
    @media(max-width: 767px){
        text-align: center;
        font-size: 16px;
    }
    @media(max-width: 480px){
        font-size: 13px;
    }
}
</style>
