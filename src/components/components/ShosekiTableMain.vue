<script setup>
// SrchHeaderからプロパティ呼び出し

const props = defineProps(['shosekiForm'])
const headers = [
    'No',
    '書籍名',
    '作者名',
    '書籍数',
    '在庫数'
]
</script>

<template>
    <main>
        書籍名一覧
        {{ props.shosekiForm }}
        <table>
            <thread>
                <tr>
                    <th v-for="(header, index) in headers"
                    v-bind:key="index">
                    {{ header }}
                </th>
                </tr>
            </thread>
            <tbody>
                <tr v-for="(book, index) in props.shosekiIchiran"
                v-bind:key="shosekiIchiran.id">
                    <th>{{ index + 1 }}</th>
                    <td>{{ shosekiIchiran.id }}</td>
                    <td>{{ shosekiIchiran.shosekiName }}</td>
                    <td>{{ shosekiIchiran.sakushaName }}</td>
                    <td>{{ shosekiIchiran.shosekiSu }}</td>
                    <td>{{ shosekiIchiran.zaikoSu }}</td>
                </tr>
            </tbody>
        </table>
    </main>
    <footer class="table">
        <small>&copy;my-vite-todo</small>
    </footer>
</template>

<style scoped>
.footer{
    margin-top: 15px;
    height: 30px;
    flex: 1;
    width: 100%;
}
</style>