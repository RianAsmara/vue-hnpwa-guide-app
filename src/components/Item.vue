<template>
  <div class="item">
    <span class="score">
      {{item.score}}
    </span>
    <span class="title">
      <a :href="item.url" target="_black" rel="noopener">{{ item.title }}</a>
    </span>
    <br />
    <span class="meta">
      <span>
        by <router-link :to="`/users/${item.by}`">{{ item.by }}</router-link>
      </span>
      <span>
        | <router-link :to="`/comments/${item.id}`">{{ item.descendants }} comments</router-link>
      </span>
    </span>
  </div>
</template>

<script>
export default {
  props: ['item']
}
</script>

<style scoped>
.item {
  background-color: #fff;
  padding: 20px 30px 20px 80px;
  border-bottom: 1px solid #eee;
  position: relative;
  line-height: 20px;
}

.score {
  font-size: 1.1em;
  font-weight: 700;
  position: absolute;
  top: 50%;
  left: 0;
  width: 80px;
  text-align: center;
  margin-top: -10px;
}

.title a {
  color: #0e0e0e;
  text-decoration: none;
}

.title a:hover {
  color: #34495e;
  text-decoration: underline;
}

.meta {
  font-size: .85em;
  color: #828282;
}

.meta a {
  color: #828282;
  text-decoration: none;
}
</style>
