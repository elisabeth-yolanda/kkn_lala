<template>
    <b-navbar class="navbar-top navbar-expand-lg" toggleable="md" style="background-color: #1388fd">
        <div class="container-md">
            <b-navbar-brand>
                <router-link to="/">
                    <img src="assets/images/GKJ Logo.png" alt="Logo" height="60" width="60" />
                </router-link>
            </b-navbar-brand>
            <div v-if="isCollapse" role="button" class="btn border-0 d-md-none" @click="toggleCollapse">
                <i class="fas fa-times font-size-30"></i>
            </div>
            <div v-else role="button" class="btn border-0 d-md-none" @click="toggleCollapse">
                <i class="fas fa-bars font-size-30"></i>
            </div>

            <b-collapse id="navBarCollapse" is-nav v-model="isCollapse">
                <ul class="navbar-nav ms-auto">
                    <li v-for="item in navbar" class="nav-item" @click="toggleCollapse(false)">
                        <router-link
                            class="nav-link text-white"
                            :class="{ 'active-link': isLinkActive(item.link) }"
                            :to="item.link"
                            exact
                        >
                            {{ item.name }}
                        </router-link>
                    </li>
                </ul>
                <b-button @click="showLoginModal">Login</b-button>
            </b-collapse>

            <b-modal
                v-model="isLoginModalVisible"
                title="Login Modal"
                ok-title="Login"
                ok-variant="success"
                cancel-title="Cancel"
                cancel-variant="danger"
                no-close-on-esc
                no-close-on-backdrop
                hide-footer

            >
                <div class="login-form">
                    <b-form @submit.prevent="login">
                        <b-form-group label="Username:" label-for="username-input">
                            <b-form-input
                                id="username-input"
                                v-model="username"
                                required
                                placeholder="Enter your username"
                            ></b-form-input>
                        </b-form-group>

                        <b-form-group label="Password:" label-for="password-input" class="mt-3">
                            <b-form-input
                                id="password-input"
                                type="password"
                                v-model="password"
                                required
                                placeholder="Enter your password"
                            ></b-form-input>
                        </b-form-group>
                        <div class="text-end mt-3">
                            <b-button @click="closeLoginModal" v-b-modal.cancel class="btn-cancel mt-3" style="background-color: red">
                                Cancel
                            </b-button>
                            <b-button type="submit" class="mt-3" v-b-modal.ok style="background-color: blue; margin-left: 3%;">
                                Login
                            </b-button>
                        </div>
                    </b-form>
                </div>
            </b-modal>
        </div>
    </b-navbar>
</template>

<script>
export default {
    data() {
        return {
            isCollapse: false,
            currentUrl: window.location.pathname,
            navbar: [
                { name: 'Dashboard', link: '/' },
                { name: 'Tentang Gereja', link: '/tentang-gereja' },
                { name: 'Layanan Jemaat', link: '/layanan-jemaat' },
                { name: 'Data Jemaat', link: '/data-jemaat' },
                { name: 'Berita', link: '/berita' },
                { name: 'Galeri Foto', link: '/galeri-foto' },
            ],
            linkBack: '',
            isLoginModalVisible: false,
            username: '',
            password: '',
        };
    },
    methods: {
        toggleCollapse() {
            this.isCollapse = !this.isCollapse;;
            const navBarCollapse = $('#navBarCollapse');
            if (this.isCollapse)
                navBarCollapse.show('slow');
            else
                navBarCollapse.hide('slow');
        },
        isLinkActive(link) {
            return this.$route.path === link;
        },
        showLoginModal() {
            this.isLoginModalVisible = true;
        },
        closeLoginModal() {
            this.isLoginModalVisible = false;
        },
    },
};
</script>

<style scoped>
button {
    background-color: #00227e;
    color: white;
    padding: 6px 18px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 15px;
    transition: background-color 0.3s;
}
.active-link {
    color: blue !important;
}

</style>
