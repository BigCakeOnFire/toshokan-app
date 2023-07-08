<script setup>
import { ref } from 'vue';
import axios from 'axios';

// 変数宣言
// 書籍名（入力）
const shosekiForm = ref('');
// 作者名（入力）
const sakushaForm = ref('');
// API(テスト用)
const urlTest = 'http://localhost:8010/getTestString';
// API
const srchUrl = 'http://localhost:8010/getSrch'

// 検索イベント
const srchEvent = () => {
    // requestparameter
    let requestparam;
    if (shosekiForm.value != null && shosekiForm.value !== '') {
        console.log(shosekiForm.value);
        requestparam = {params:{
            shosekiName: shosekiForm.value,
            sakushaName: ''
        }}
        console.log(requestparam);
        //axios.get(srchUrl, {requestparam})
        axios.get(srchUrl, requestparam)
        .then(response => {
                console.log(response);
                console.log('レスポンスあり');
            })
            .catch(error => {
                console.log(error);
                console.log('エラー');
        })
    } else {
        console.log('書籍空');
    }
    if (sakushaForm.value != null && sakushaForm.value !== '') {
        console.log(sakushaForm.value);
        requestparam = { params:{
                shosekiName: '',
                sakushaName: sakushaForm.value
        }}
        axios.get(srchUrl, requestparam )
            .then(response => {
                console.log(response);
            })
            .catch(error => {
                console.log(error);
            })
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