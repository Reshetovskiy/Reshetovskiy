<template>
    <main>
        <section class="contact" id="contact">
            <div class="container content">
                <h1 class="contact__title">We're an independent development agency.</h1>
                <p class="contact__text text">
                    We understand the intricacies of web development inside-out.
                    That's why we build rock-solid Mobile and Web applications enriched with user-centered visual experiences.
                </p>
                <button class="contact__button c-button">Contact Us</button>
            </div>
        </section>
        <section class="section" id="secvices">
            <div class="container">
                <h2 class="title"> <span> OUR SERVICES </span></h2>
                <div class="services__content content">
                    <div class="services-item">
                        <figure class="services-item__frame">
                            <img src="../assets/images/phone.svg" alt class="services-item__img" />
                        </figure>
                        <div class="services-item__description">
                            <h3 class="services-item__title">Mobile Development</h3>
                            <p class="services-item__text">
                                We develop mobile apps for all contemporary mobile platforms. Mamon team builds native and cross-platform solutions.
                            </p>
                        </div>
                    </div>
                    <div class="services-item">
                        <figure class="services-item__frame">
                            <img src="../assets/images/monitor.svg" alt class="services-item__img" />
                        </figure>
                        <div class="services-item__description">
                            <h3 class="services-item__title">Web Development</h3>
                            <p class="services-item__text"> Mamon offers full range of services from various CMS and frameworks based websites to complex ERP/CRM solutions and e-commerce stores.</p>
                        </div>
                    </div>
                    <div class="services-item">
                        <figure class="services-item__frame">
                            <img src="../assets/images/new.svg" alt class="services-item__img" />
                        </figure>
                        <div class="services-item__description">
                            <h3 class="services-item__title">Product Design</h3>
                            <p class="services-item__text">We create design given the product audience, goal, business domain, technology and the platform for the solution.</p>
                        </div>
                    </div>
                    <div class="services-item">
                        <figure class="services-item__frame">
                            <img src="../assets/images/test.svg" alt class="services-item__img" />
                        </figure>
                        <div class="services-item__description">
                            <h3 class="services-item__title">Quality Assurance</h3>
                            <p class="services-item__text">Our QA team ensures high standard of quality of products delivered.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="clients" id="clients">
        <div class="container">
            <h2 class="title"><span> OUR CLIENTS </span></h2>
            <div class="clients__content content">
                <a href="#" class="clients-item">
                    <img src="../assets/images/client1.svg" alt="" class="clients-item__img">
                </a>
                <a href="#" class="clients-item">
                    <img src="../assets/images/client2.svg" alt="" class="clients-item__img">
                </a>
                <a href="#" class="clients-item">
                    <img src="../assets/images/client3.svg" alt="" class="clients-item__img">
                </a>
                <a href="#" class="clients-item">
                    <img src="../assets/images/client4.svg" alt="" class="clients-item__img">
                </a>
                <a href="#" class="clients-item">
                    <img src="../assets/images/client5.svg" alt="" class="clients-item__img">
                </a>
                <a href="#" class="clients-item">
                    <img src="../assets/images/client6.svg" alt="" class="clients-item__img">
                </a>
                <a href="#" class="clients-item">
                    <img src="../assets/images/client7.svg" alt="" class="clients-item__img">
                </a>
                <a href="#" class="clients-item">
                    <img src="../assets/images/client8.svg" alt="" class="clients-item__img">
                </a>
                <a href="#" class="clients-item">
                    <img src="../assets/images/client9.svg" alt="" class="clients-item__img">
                </a>
                <a href="#" class="clients-item">
                    <img src="../assets/images/client10.svg" alt="" class="clients-item__img">
                </a>
                <a href="#" class="clients-item">
                    <img src="../assets/images/client11.svg" alt="" class="clients-item__img">
                </a>
                <a href="#" class="clients-item">
                    <img src="../assets/images/client12.svg" alt="" class="clients-item__img">
                </a>
            </div>
        </div>
        </section>
        <section class="team" id="team">
            <div class="container">
                <h2 class="title"> <span> OUR TEAM </span></h2>
                <div class="team__content content">
                <div class="team-item" v-for="(item, index) in team.results" :key="index">
                    <figure class="team-item__frame"><img :src="item.picture.large" alt="" class="team-item__img"></figure>
                    <div class="team-item__description">
                        <h4 class="team-item__name"> {{item.name.first}} {{item.name.last}}</h4>
                        <span class="team-item__position">{{item.location.city}}</span>
                    </div>
                </div>
                </div>
            </div>
        </section>
    </main>
</template>

<script>
export default {
    data: () => ({
        team: [], 
    }), 
    async mounted() {
        this.team = await this.$axios.$get('https://randomuser.me/api/?results=9');
    }
};
</script>

<style>
</style>
