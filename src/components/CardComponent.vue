<template>
  <div class="card">
  <div class="card-header">
    Card Header
  </div>
  <div class="card-content">
    <slot>Default Content</slot>
  </div>
  <div class="card-footer">
    <button class="btn">Action 1</button>
    <button class="btn">Action 2</button>
  </div>
</div>
</template>

<script>
export default {
    name: 'CardComponent',
};
</script>

<style>
/* Card Container */
.card {
  border: 1px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  width: 300px;
  margin: 20px;
  background-color: #fff;
  transition: box-shadow 0.3s ease;
}

.card:hover {
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

/* Card Header */
.card-header {
  background-color: #f5f5f5;
  padding: 10px 15px;
  font-size: 18px;
  font-weight: bold;
  border-bottom: 1px solid #ddd;
}

/* Card Image */
.card-image {
  width: 100%;
  height: auto;
  display: block;
}

/* Card Content */
.card-content {
  padding: 15px;
  font-size: 16px;
  color: #333;
}

/* Card Footer */
.card-footer {
  padding: 10px 15px;
  border-top: 1px solid #ddd;
  background-color: #f5f5f5;
  text-align: right;
}

/* Buttons */
.btn {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 8px 12px;
  margin: 5px;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.btn:hover {
  background-color: #0056b3;
}
</style>