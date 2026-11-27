<script setup>
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'

const menuOpen = ref(false)

const navLinks = [
  { path: '/', label: '首页' },
  { path: '/about', label: '关于我们' },
  { path: '/services', label: '业务范围' },
  { path: '/contact', label: '联系我们' },
]

function toggleMenu() {
  menuOpen.value = !menuOpen.value
}

function closeMenu() {
  menuOpen.value = false
}
</script>

<template>
  <div class="app-shell">
    <header class="site-header">
      <div class="container header-inner">
        <RouterLink to="/" class="brand" @click="closeMenu">星辰科技</RouterLink>

        <button
          class="menu-toggle"
          :class="{ 'is-open': menuOpen }"
          type="button"
          aria-label="切换导航菜单"
          :aria-expanded="menuOpen"
          @click="toggleMenu"
        >
          <span></span>
          <span></span>
          <span></span>
        </button>

        <nav class="nav" :class="{ 'is-open': menuOpen }">
          <RouterLink
            v-for="link in navLinks"
            :key="link.path"
            :to="link.path"
            class="nav-link"
            @click="closeMenu"
          >
            {{ link.label }}
          </RouterLink>
        </nav>
      </div>
    </header>

    <main class="site-main">
      <RouterView />
    </main>

    <footer class="site-footer">
      <div class="container footer-inner">
        <p>&copy; {{ new Date().getFullYear() }} 星辰科技有限公司. 保留所有权利.</p>
        <p class="footer-sub">地址：上海市浦东新区科技路 100 号 &nbsp;|&nbsp; 电话：400-800-1234</p>
      </div>
    </footer>
  </div>
</template>

<style scoped>
.app-shell {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.site-header {
  position: sticky;
  top: 0;
  z-index: 100;
  background: #fff;
  border-bottom: 1px solid var(--color-border);
}

.header-inner {
  height: var(--header-height);
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.brand {
  font-size: 20px;
  font-weight: 700;
  color: var(--color-primary);
}

.nav {
  display: flex;
  gap: 32px;
}

.nav-link {
  font-size: 15px;
  font-weight: 500;
  color: var(--color-text-muted);
  padding: 8px 0;
  position: relative;
}

.nav-link:hover,
.nav-link.router-link-active {
  color: var(--color-primary);
}

.menu-toggle {
  display: none;
  flex-direction: column;
  justify-content: center;
  gap: 5px;
  width: 32px;
  height: 32px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
}

.menu-toggle span {
  display: block;
  width: 100%;
  height: 2px;
  background: var(--color-text);
  transition: transform 0.2s ease, opacity 0.2s ease;
}

.menu-toggle.is-open span:nth-child(1) {
  transform: translateY(7px) rotate(45deg);
}

.menu-toggle.is-open span:nth-child(2) {
  opacity: 0;
}

.menu-toggle.is-open span:nth-child(3) {
  transform: translateY(-7px) rotate(-45deg);
}

.site-main {
  flex: 1;
}

.site-footer {
  background: var(--color-text);
  color: #cdd3e0;
  padding: 24px 0;
}

.footer-inner {
  text-align: center;
  font-size: 13px;
}

.footer-sub {
  margin-top: 6px;
  color: #9aa3b5;
}

@media (max-width: 768px) {
  .menu-toggle {
    display: flex;
  }

  .nav {
    position: absolute;
    top: var(--header-height);
    left: 0;
    right: 0;
    flex-direction: column;
    gap: 0;
    background: #fff;
    border-bottom: 1px solid var(--color-border);
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.25s ease;
  }

  .nav.is-open {
    max-height: 320px;
  }

  .nav-link {
    padding: 14px 24px;
    border-top: 1px solid var(--color-border);
  }
}
</style>
