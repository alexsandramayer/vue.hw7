<template>
    <header class="header container">
        <div class="header__top">
            <HeaderBlock />
        </div>
    </header> 

    <div class="banner banner__project">
        <div class="banner__block">
            <h1 class="banner__title">Our Project</h1>
            <div class="banner__breadcrumbs">
                <div class="banner__breadcrumb">Home</div>
                <div class="banner__breadcrumb">Project</div>
            </div>
        </div>
    </div>

    <div class="categories container">
        <div class="categories__btns">
            <button :class="[tag.isActive ? 'btn-active' : ''] + ' ' + 'categories__btn' "
                v-for="tag in tags" @click="clickTag(tag.id)"> {{tag.name}}
            </button>
        </div>
        <div class="categories__block">
            <ProjectComp v-for="article in currenTagArticles" :article="article"
        :clickFav="clickFav" />
        </div>

        <div class="pagination">
                <ul class="pagination__ul">
                    <li>01</li>
                    <li>02</li>
                    <li>03</li>
                    <li><svg xmlns="http://www.w3.org/2000/svg" width="53" height="52" viewBox="0 0 53 52" fill="none">
                        <circle cx="26.5" cy="26" r="25.5" stroke="#CDA274"/>
                        <path d="M23.5571 32L29.5 25.3143L23.5571 18.6286" stroke="#292F36" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                      </svg></li>
                </ul>
            </div>
    </div>

    <footer class="footer  container">
        <FooterBlock />
        <!-- <div class="footer__info">
            <a href="#" class="logo"><img :src="logo" alt="logo"></a>
            <div class="footer__descr">It is a long established fact that a reader will be distracted lookings.</div>
            <div class="footer__social">
                <a class="footer__social_twitter" href="#">
                    <svg fill="#000000" viewBox="0 0 32 32" version="1.1" xmlns="http://www.w3.org/2000/svg"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <title>twitter</title> <path d="M30.917 6.728c-1.026 0.465-2.217 0.805-3.464 0.961l-0.061 0.006c1.268-0.771 2.222-1.952 2.687-3.354l0.013-0.044c-1.124 0.667-2.431 1.179-3.82 1.464l-0.082 0.014c-1.123-1.199-2.717-1.946-4.485-1.946-3.391 0-6.14 2.749-6.14 6.14 0 0.496 0.059 0.979 0.17 1.441l-0.008-0.042c-5.113-0.254-9.613-2.68-12.629-6.366l-0.025-0.031c-0.522 0.873-0.831 1.926-0.831 3.052 0 0.013 0 0.026 0 0.039v-0.002c0 0.001 0 0.003 0 0.005 0 2.12 1.075 3.989 2.709 5.093l0.022 0.014c-1.026-0.034-1.979-0.315-2.811-0.785l0.031 0.016v0.075c0 0.001 0 0.002 0 0.002 0 2.961 2.095 5.434 4.884 6.014l0.040 0.007c-0.484 0.135-1.040 0.212-1.614 0.212-0.406 0-0.802-0.039-1.186-0.113l0.039 0.006c0.813 2.459 3.068 4.212 5.739 4.264l0.006 0c-2.072 1.638-4.721 2.627-7.602 2.627-0.005 0-0.009 0-0.014 0h0.001c-0.515-0.001-1.022-0.031-1.521-0.089l0.061 0.006c2.663 1.729 5.92 2.757 9.418 2.757 0.005 0 0.009 0 0.014 0h-0.001c0.037 0 0.082 0 0.126 0 9.578 0 17.343-7.765 17.343-17.343 0-0.039-0-0.077-0-0.116l0 0.006c0-0.262 0-0.524-0.019-0.786 1.21-0.878 2.229-1.931 3.042-3.136l0.028-0.044z"></path></g></svg></a>
                <a class="footer__social_linkedin" href="#">
                    <svg fill="#000000" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 512 512" xml:space="preserve"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <g id="7935ec95c421cee6d86eb22ecd125aef"> <path style="display: inline; fill-rule: evenodd; clip-rule: evenodd;" d="M116.504,500.219V170.654H6.975v329.564H116.504 L116.504,500.219z M61.751,125.674c38.183,0,61.968-25.328,61.968-56.953c-0.722-32.328-23.785-56.941-61.252-56.941 C24.994,11.781,0.5,36.394,0.5,68.722c0,31.625,23.772,56.953,60.53,56.953H61.751L61.751,125.674z M177.124,500.219 c0,0,1.437-298.643,0-329.564H286.67v47.794h-0.727c14.404-22.49,40.354-55.533,99.44-55.533 c72.085,0,126.116,47.103,126.116,148.333v188.971H401.971V323.912c0-44.301-15.848-74.531-55.497-74.531 c-30.254,0-48.284,20.38-56.202,40.08c-2.897,7.012-3.602,16.861-3.602,26.711v184.047H177.124L177.124,500.219z"> </path> </g> </g></svg>
                </a>
            </div>
        </div>
        <div class="footer__pages">
            <h3 class="footer__title">Pages</h3>
            <nav class="nav__footer">
                <ul class="nav__list_footer">
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Project</a></li>
                    <li><a href="#">Blog</a></li>
                </ul>
            </nav>
        </div>
        <div class="footer__contact">
            <h3 class="footer__title">Contact</h3>
            <div class="footer__contact_adress">55 East Birchwood Ave. Brooklyn, New York 11201</div>
            <a class="footer__contact_email">contact@interno.com</a>
            <a class="footer__contact_tel" href="tel:1234567890">(123) 456 - 7890</a>

        </div> -->
    </footer>
</template>

<script>
import HeaderBlock from './HeaderBlock.vue';
import FooterBlock from './FooterBlock.vue';
import { v4 as uuidv4 } from 'uuid';
import ProjectComp from './ProjectComp.vue';

    export default {
        name: 'ProjectPage',
        components: {
            HeaderBlock,
            FooterBlock,
            ProjectComp
        },
        
        data() {
            return {
                tags: [
                    {
                        id: 1,
                        name: 'Bathroom',
                        isActive: false,
                    },
                    {
                        id: 2,
                        name: 'Bedroom',
                        isActive: false,
                    },
                    {
                        id: 3,
                        name: 'Kitchen',
                        isActive: false,
                    },
                    {
                        id: 4,
                        name: 'Living Area',
                        isActive: false,
                    }
                ],
                articles: [
                    {
                        id: uuidv4(),
                        tag: 'Bedroom',
                        img: require('@/assets/images/project_page_img/project__bedroom1.png'),
                        title: 'Minimal Bedroom',
                        subtitle: 'Decor / Artchitecture',
                        favorite: true,
                    },
                    {
                        id: uuidv4(),
                        tag: 'Bedroom',
                        img: require('@/assets/images/project_page_img/project__bedroom2.png'),
                        title: 'Minimal Bedroom',
                        subtitle: 'Decor / Artchitecture',
                        favorite: false,
                    },
                    {
                        id: uuidv4(),
                        tag: 'Bedroom',
                        img: require('@/assets/images/project_page_img/project__bedroom3.png'),
                        title: 'Classic Minimal Bedroom',
                        subtitle: 'Decor / Artchitecture',
                        favorite: false,
                    },
                    {
                        id: uuidv4(),
                        tag: 'Bedroom',
                        img: require('@/assets/images/project_page_img/project__bedroom4.png'),
                        title: 'Modern Bedroom',
                        subtitle: 'Decor / Artchitecture',
                        favorite: true,
                    },
                    {
                        id: uuidv4(),
                        tag: 'Bedroom',
                        img: require('@/assets/images/project_page_img/project__bedroom5.png'),
                        title: 'Minimal Bedroom table',
                        subtitle: 'Decor / Artchitecture',
                        favorite: false,
                    },
                    {
                        id: uuidv4(),
                        tag: 'Bedroom',
                        img: require('@/assets/images/project_page_img/project__bedroom6.png'),
                        title: 'System Table',
                        subtitle: 'Decor / Artchitecture',
                        favorite: false,
                    },
                    {
                        id: uuidv4(),
                        tag: 'Bedroom',
                        img: require('@/assets/images/project_page_img/project__bedroom7.png'),
                        title: 'Modern Bedroom',
                        subtitle: 'Decor / Artchitecture',
                        favorite: false,
                    },
                    {
                        id: uuidv4(),
                        tag: 'Bedroom',
                        img: require('@/assets/images/project_page_img/project__bedroom8.png'),
                        title: 'Modern Bedroom',
                        subtitle: 'Decor / Artchitecture',
                        favorite: false,
                    },
                ],
                currenTagArticles: [],
                favoriteArticles: [],
            }
        },
        methods: {
            clickTag(id) {
                const tags = this.tags
                for (let i = 0; i < tags.length; i++) {
                    tags[i].isActive = tags[i].id === id;
                    if(tags[i].id === id) {this.filterTagArticles(tags[i].name)};
                }
            },
            clickFav(id) {
                const articles = this.articles;
                for (let i = 0; i < articles.length; i++) {
                    if(articles[i].id === id) {
                        articles[i].favorite = !articles[i].favorite;
                    }
                }
                this.filterFavArticles()
            },
            filterFavArticles() {
                return this.favoriteArticles = this.articles.filter((art) => art.favorite === true);
            },
            filterTagArticles(tag) {
                return this.currenTagArticles = this.articles.filter((art) => art.tag === tag);
            }
        },
        created() {
            this.currenTagArticles = this.articles;
        } 
    }
</script>

<style lang="scss" scoped>

</style>