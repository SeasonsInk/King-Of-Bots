<template>
  <nav
    class="navbar navbar-expand-lg bg-dark bg-body-tertiary"
    data-bs-theme="dark"
  >
    <div class="container-fluid">
      <router-link class="navbar-brand" :to="{ name: 'home' }"
        >King Of Bots</router-link
      >
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarText"
        aria-controls="navbarText"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarText">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <router-link
              :class="route_name == 'pk_index' ? 'nav-link active' : 'nav-link'"
              aria-current="page"
              :to="{ name: 'pk_index' }"
              >对战</router-link
            >
          </li>
          <li class="nav-item">
            <router-link
              :class="
                route_name == 'record_index' ? 'nav-link active' : 'nav-link'
              "
              :to="{ name: 'record_index' }"
              >对局列表</router-link
            >
          </li>
          <li class="nav-item">
            <router-link
              :class="
                route_name == 'ranklist_index' ? 'nav-link active' : 'nav-link'
              "
              :to="{ name: 'ranklist_index' }"
              >排行榜</router-link
            >
          </li>
        </ul>
        <ul class="navbar-nav me-4">
          <li class="nav-item dropdown-center">
            <router-link
              class="nav-link dropdown-toggle"
              href="#"
              role="button"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              WJL
            </router-link>
            <ul class="dropdown-menu" style="min-width: 90px">
              <li>
                <router-link
                  class="dropdown-item"
                  :to="{ name: 'user_bot_index' }"
                  >我的Bot</router-link
                >
              </li>
              <li>
                <router-link class="dropdown-item" href="#">退出</router-link>
              </li>
            </ul>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
import { useRoute } from "vue-router";
import { computed } from "vue";

export default {
  setup() {
    const route = useRoute();
    let route_name = computed(() => route.name);
    return {
      route_name,
    };
  },
};
</script>

<style scoped></style>
