<script setup>
import SrchHeader from './components/SrchHeader.vue';
import ShosekiTableMain from './components/ShosekiTableMain.vue';
</script>
<template>
    <div class="wrap">
        <div>ヘッダー</div>
        <SrchHeader />
        <ShosekiTableMain />
        <main class="main">メイン</main>
        <div>フッター</div>
    </div>
</template>

<style>
@import 'assets/css/destyle.css-3.0.2/';
.wrap{
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;
    width: 600px;
    margin: 0 auto;
    font-family: sans-serif;
}

.main{
    flex: 1;
    width: 100%;
}
</style>