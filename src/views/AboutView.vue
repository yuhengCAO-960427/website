<script setup>
const timeline = [
  { year: '2015', text: '公司成立，专注企业软件定制开发' },
  { year: '2018', text: '业务拓展至云服务与运维支持' },
  { year: '2021', text: '服务客户数突破 300 家' },
  { year: '2024', text: '完成数字化转型咨询品牌升级' },
]
</script>

<template>
  <div>
    <section class="page-header">
      <div class="container">
        <h1>关于我们</h1>
        <p>一家专注于企业数字化服务的技术公司</p>
      </div>
    </section>

    <section class="section">
      <div class="container about-grid">
        <div class="about-text">
          <h2>公司简介</h2>
          <p>
            星辰科技成立于 2015 年，致力于为企业提供从软件开发、云基础设施到数字化转型咨询的全链路服务。
            我们始终坚持以客户需求为中心，用专业能力和高效执行帮助客户在竞争中保持领先。
          </p>
          <p>
            目前，公司拥有一支经验丰富的技术团队，已成功为超过 500 家企业客户提供过服务，
            覆盖金融、零售、制造等多个行业。
          </p>
        </div>
        <div class="about-stats">
          <div class="stat-item">
            <strong>500+</strong>
            <span>服务客户</span>
          </div>
          <div class="stat-item">
            <strong>10+</strong>
            <span>行业年限</span>
          </div>
          <div class="stat-item">
            <strong>98%</strong>
            <span>客户满意度</span>
          </div>
        </div>
      </div>
    </section>

    <section class="section section-alt">
      <div class="container">
        <h2 class="section-title">发展历程</h2>
        <ul class="timeline">
          <li v-for="item in timeline" :key="item.year" class="timeline-item">
            <span class="timeline-year">{{ item.year }}</span>
            <span class="timeline-text">{{ item.text }}</span>
          </li>
        </ul>
      </div>
    </section>
  </div>
</template>

<style scoped>
.page-header {
  background: var(--color-bg-alt);
  padding: 56px 0;
  text-align: center;
}

.page-header h1 {
  margin: 0 0 8px;
  font-size: 32px;
}

.page-header p {
  margin: 0;
  color: var(--color-text-muted);
}

.about-grid {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 40px;
  align-items: start;
}

.about-text h2 {
  margin-top: 0;
}

.about-text p {
  color: var(--color-text-muted);
}

.about-stats {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.stat-item {
  background: var(--color-bg-alt);
  border-radius: 10px;
  padding: 20px;
  text-align: center;
}

.stat-item strong {
  display: block;
  font-size: 28px;
  color: var(--color-primary);
}

.stat-item span {
  font-size: 13px;
  color: var(--color-text-muted);
}

.timeline {
  list-style: none;
  max-width: 640px;
  margin: 0 auto;
}

.timeline-item {
  display: flex;
  gap: 20px;
  padding: 16px 0;
  border-bottom: 1px solid var(--color-border);
}

.timeline-item:last-child {
  border-bottom: none;
}

.timeline-year {
  font-weight: 700;
  color: var(--color-primary);
  min-width: 60px;
}

.timeline-text {
  color: var(--color-text-muted);
}

@media (max-width: 768px) {
  .about-grid {
    grid-template-columns: 1fr;
  }

  .about-stats {
    flex-direction: row;
    flex-wrap: wrap;
  }

  .stat-item {
    flex: 1 1 calc(50% - 10px);
  }
}
</style>
