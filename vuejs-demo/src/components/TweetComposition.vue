<template>
    <div class="tweet">
      <div class="tweet-content">
        <h3>{{ username }}</h3>
        <p>{{ content }}</p>
        <span>{{ publishedAt }}</span>
      </div>
      <button @click="toggleLike">{{ isLiked ? 'Liked' : 'Like' }}</button>
    </div>
</template>
  
  <script setup>
    import { ref, defineProps } from 'vue';
    const props = defineProps({
        username: String,
        content: String,
        publishedAt: String
    });
  
    const isLiked = ref(false);
    
    const toggleLike = () => {
        isLiked.value = !isLiked.value;
    };
  </script>
  
 
  <style>
   /* Estils del component */

        .tweet {
        display: flex;
        justify-content: space-between;
        align-items: center;
        border: 1px solid #e1e8ed;
        border-radius: 10px;
        padding: 10px 15px;
        margin-bottom: 10px;
        background-color: #fff;
        max-width: 500px;
    }

    .tweet-content {
        padding-right: 20px;
    }

    .tweet h3 {
        margin: 0;
        padding-bottom: 5px;
        font-size: 16px;
        color: #41D688;
        font-weight: bold;
    }

    .tweet p {
        margin: 0;
        padding: 5px 0;
        font-size: 14px;
        color: #14171a;
    }

    .tweet span {
        font-size: 12px;
        color: #657786;
        right: 80%;
    }

    .tweet button {
        background-color: #41D688;
        border: none;
        border-radius: 15px;
        border: 1px solid #033b1e56;
        padding: 5px 20px;
        color: white;
        cursor: pointer;
        font-size: 14px;
    }

    .tweet button:hover {
        background-color: #369966;
        transition: 0.3s;
    }
  </style>
  