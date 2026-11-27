<script setup>
import { reactive, ref } from 'vue'

const form = reactive({
  name: '',
  phone: '',
  message: '',
})

const submitted = ref(false)

function handleSubmit() {
  submitted.value = true
}
</script>

<template>
  <div>
    <section class="page-header">
      <div class="container">
        <h1>联系我们</h1>
        <p>我们期待与您的合作</p>
      </div>
    </section>

    <section class="section">
      <div class="container contact-grid">
        <div class="contact-info">
          <h2>联系方式</h2>
          <ul class="info-list">
            <li><strong>电话：</strong>400-800-1234</li>
            <li><strong>邮箱：</strong>contact@starcompany.com</li>
            <li><strong>地址：</strong>上海市浦东新区科技路 100 号</li>
            <li><strong>工作时间：</strong>周一至周五 9:00-18:00</li>
          </ul>
        </div>

        <form class="contact-form" @submit.prevent="handleSubmit">
          <h2>在线留言</h2>

          <p v-if="submitted" class="success-msg">提交成功，我们会尽快与您联系！</p>

          <div class="form-field">
            <label for="name">姓名</label>
            <input id="name" v-model="form.name" type="text" required placeholder="请输入您的姓名" />
          </div>

          <div class="form-field">
            <label for="phone">联系电话</label>
            <input id="phone" v-model="form.phone" type="tel" required placeholder="请输入您的联系电话" />
          </div>

          <div class="form-field">
            <label for="message">留言内容</label>
            <textarea
              id="message"
              v-model="form.message"
              rows="4"
              required
              placeholder="请描述您的需求"
            ></textarea>
          </div>

          <button type="submit" class="btn btn-primary submit-btn">提交留言</button>
        </form>
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

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1.3fr;
  gap: 40px;
}

.contact-info h2,
.contact-form h2 {
  margin-top: 0;
}

.info-list {
  list-style: none;
  color: var(--color-text-muted);
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.info-list strong {
  color: var(--color-text);
}

.contact-form {
  background: var(--color-bg-alt);
  border-radius: 12px;
  padding: 28px;
}

.form-field {
  margin-bottom: 18px;
}

.form-field label {
  display: block;
  font-size: 14px;
  font-weight: 600;
  margin-bottom: 6px;
}

.form-field input,
.form-field textarea {
  width: 100%;
  padding: 10px 14px;
  border: 1px solid var(--color-border);
  border-radius: 8px;
  font-size: 14px;
  font-family: inherit;
  resize: vertical;
}

.form-field input:focus,
.form-field textarea:focus {
  outline: none;
  border-color: var(--color-primary);
}

.submit-btn {
  width: 100%;
}

.success-msg {
  background: #e7f7ee;
  color: #1a8f52;
  padding: 10px 14px;
  border-radius: 8px;
  font-size: 14px;
  margin-bottom: 18px;
}

@media (max-width: 768px) {
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 28px;
  }

  .contact-form {
    padding: 20px;
  }
}
</style>
