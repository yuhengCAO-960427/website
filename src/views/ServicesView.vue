<script setup>
const services = [
  {
    title: '定制软件开发',
    desc: '面向企业业务场景的 Web / 移动端应用定制开发，涵盖需求分析、设计、开发与交付全流程。',
  },
  {
    title: '云服务与运维',
    desc: '提供云基础设施搭建、部署自动化与持续运维保障，确保业务系统稳定运行。',
  },
  {
    title: '数字化转型咨询',
    desc: '结合行业经验，为企业提供数字化战略规划与落地实施建议。',
  },
  {
    title: '系统集成',
    desc: '打通企业内部多套系统间的数据与流程壁垒，提升整体协同效率。',
  },
  {
    title: 'UI / UX 设计',
    desc: '以用户体验为核心，提供产品界面设计与交互优化服务。',
  },
  {
    title: '技术支持与培训',
    desc: '7x24 技术支持响应，并为客户团队提供系统使用与维护培训。',
  },
]
</script>

<template>
  <div>
    <section class="page-header">
      <div class="container">
        <h1>业务范围</h1>
        <p>覆盖企业数字化全链路的专业服务</p>
      </div>
    </section>

    <section class="section">
      <div class="container">
        <div class="service-grid">
          <div v-for="item in services" :key="item.title" class="service-card">
            <h3>{{ item.title }}</h3>
            <p>{{ item.desc }}</p>
          </div>
        </div>
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

.service-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}

.service-card {
  background: #fff;
  border: 1px solid var(--color-border);
  border-radius: 12px;
  padding: 28px;
  transition: box-shadow 0.2s ease, transform 0.2s ease;
}

.service-card:hover {
  box-shadow: 0 8px 24px rgba(20, 30, 60, 0.08);
  transform: translateY(-2px);
}

.service-card h3 {
  margin: 0 0 10px;
  font-size: 18px;
  color: var(--color-primary);
}

.service-card p {
  margin: 0;
  color: var(--color-text-muted);
  font-size: 14px;
}

@media (max-width: 768px) {
  .service-grid {
    grid-template-columns: 1fr;
    gap: 16px;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .service-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
