<script setup>
const highlights = [
  { title: '10+ 年行业经验', desc: '深耕技术服务领域，服务超过 500 家企业客户。' },
  { title: '专业技术团队', desc: '核心团队来自一线互联网企业，经验丰富。' },
  { title: '7x24 技术支持', desc: '全天候响应，保障业务稳定运行。' },
]
</script>

<template>
  <div>
    <section class="hero">
      <div class="container hero-inner">
        <h1 class="hero-title">用技术驱动企业增长</h1>
        <p class="hero-subtitle">
          我们为企业提供软件开发、云服务与数字化转型解决方案，助力业务高效落地。
        </p>
        <div class="hero-actions">
          <RouterLink to="/contact" class="btn btn-primary">立即咨询</RouterLink>
          <RouterLink to="/services" class="btn btn-outline">了解业务</RouterLink>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="container">
        <h2 class="section-title">为什么选择我们</h2>
        <p class="section-subtitle">专注品质与效率，为客户创造可持续的业务价值</p>
        <div class="highlight-grid">
          <div v-for="item in highlights" :key="item.title" class="highlight-card">
            <h3>{{ item.title }}</h3>
            <p>{{ item.desc }}</p>
          </div>
        </div>
      </div>
    </section>

    <section class="section section-alt">
      <div class="container cta-inner">
        <h2>准备好开启合作了吗？</h2>
        <p>联系我们的团队，获取专属解决方案</p>
        <RouterLink to="/contact" class="btn btn-primary">联系我们</RouterLink>
      </div>
    </section>
  </div>
</template>

<style scoped>
.hero {
  background: linear-gradient(135deg, #2f6fed 0%, #1d4fc4 100%);
  color: #fff;
  padding: 96px 0;
  text-align: center;
}

.hero-title {
  font-size: 44px;
  font-weight: 800;
  margin: 0 0 16px;
}

.hero-subtitle {
  font-size: 17px;
  max-width: 560px;
  margin: 0 auto 32px;
  opacity: 0.92;
}

.hero-actions {
  display: flex;
  gap: 16px;
  justify-content: center;
  flex-wrap: wrap;
}

.hero .btn-outline {
  border-color: rgba(255, 255, 255, 0.6);
  color: #fff;
}

.hero .btn-outline:hover {
  border-color: #fff;
  color: #fff;
}

.highlight-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}

.highlight-card {
  background: #fff;
  border: 1px solid var(--color-border);
  border-radius: 12px;
  padding: 28px;
  text-align: center;
}

.highlight-card h3 {
  margin: 0 0 10px;
  font-size: 18px;
}

.highlight-card p {
  margin: 0;
  color: var(--color-text-muted);
  font-size: 14px;
}

.cta-inner {
  text-align: center;
}

.cta-inner h2 {
  font-size: 28px;
  margin: 0 0 8px;
}

.cta-inner p {
  color: var(--color-text-muted);
  margin: 0 0 24px;
}

@media (max-width: 768px) {
  .hero {
    padding: 56px 0;
  }

  .hero-title {
    font-size: 28px;
  }

  .hero-subtitle {
    font-size: 15px;
  }

  .highlight-grid {
    grid-template-columns: 1fr;
    gap: 16px;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .highlight-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
