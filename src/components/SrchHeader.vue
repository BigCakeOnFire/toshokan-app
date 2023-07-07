<script setup>
import { ref } from 'vue';
// 変数宣言
const shosekiForm = ref('');
const sakushaForm = ref('');

// 検索イベント
const srchEvent = () => {
    if (shosekiForm.value != null && shosekiForm.value !== '') {
        console.log(shosekiForm.value);
    } else {
        console.log('書籍空');
    }
    if (sakushaForm.value != null && sakushaForm.value !== '') {
        console.log(sakushaForm.value);
    } else {
        console.log('作者空');
    }

}
</script>

<template>
    <h1 class="title">書籍検索</h1>
    <div class="srch">
        <input type="text" class="form" v-model="shosekiForm" placeholder="+書籍名を入力" />
        <input type="text" class="form" v-model="sakushaForm" placeholder="+作者名を入力" />
        <button class="btn" @click="srchEvent">検索</button>
    </div>
    {{ shosekiForm }}
    {{ sakushaForm }}
</template>

<style scoped>
.title{
    width: 100%;
    background-color: #e3f2fd;
    text-align: center;
    font-size: 32px;
    font-weight: bold;
    padding: 8px 0;
}

.form{
    background-color: green;
}
.srch{
    float: left;
}
.btn{
    padding: 8px;
    background-color: rgb(59, 228, 59);
    border-radius: 6px;
    color: white;
    text-align: center;
    font-size: 14px;
}
</style>