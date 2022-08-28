<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <!-- Container wrapper -->
        <div class="container-fluid">
            <!-- Toggle button -->
            <button class="navbar-toggler" type="button" data-mdb-toggle="collapse"
                data-mdb-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false"
                aria-label="Toggle navigation">
                <i class="fas fa-bars"></i>
            </button>

            <!-- Collapsible wrapper -->
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <a class="nav-link" href="#">Dashboard</a>
                    </li>

                </ul>

            </div>

            <div class="d-flex align-items-center">

                <div class="dropdown">
                    <a class="dropdown-toggle d-flex align-items-center hidden-arrow" href="#"
                        id="navbarDropdownMenuAvatar" role="button" data-mdb-toggle="dropdown" aria-expanded="false">

                    </a>
                    <ul class="dropdown-menu dropdown-menu-end" aria-labelledby="navbarDropdownMenuAvatar">

                        <li v-for="item in nav[0].drop" :key="item.uid">
                            <a class="dropdown-item" href="#">{{ item.id }}</a>
                        </li>

                    </ul>
                </div>
            </div>
            <!-- Right elements -->
        </div>
        <!-- Container wrapper -->
    </nav>
</template>

<script>
export default {
    data() {
        return {
            nav: [
                {
                    uid: 1,
                    name: "home",
                    path: "/",
                    drop: [{
                        id: 1,
                        s: 'item1'
                    }, {
                        id: 2,
                        s: 'item2'
                    }, {
                        id: 3,
                        s: 'item3'
                    }]

                },
                {
                    uid: 2,
                    name: "about",
                    path: "/about"
                },
                {
                    uid: 3,
                    name: "contact",
                    path: "/contact"
                }
            ],
        }
    }
}
</script>
<style lang="css" scoped>
.nav-list {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
    list-style: none;
    width: 100%;
    border: 2px solid red;
}
</style>