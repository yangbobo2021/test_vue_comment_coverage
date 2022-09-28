<template>
    <div>
        <HelloWorld msg="我是index" />
        <div>访问首页次数：{{count}}</div>
        <div @click="toList" :class="styles.blue">跳转到list</div>
        <div @click="toHook" :class="styles.red">跳转到hook</div>
    </div>
</template>

<script setup>
// router
import {
    useRoute,
    useRouter
} from "vue-router";
// Router
const router = useRouter();
// Route
const route = useRoute()
// 跳转到列表页
const toList =
// 跳转到列表页
() => {
    router.push({
        name: 'list'
    })
};
// 跳转到hook页面
const toHook =
// 跳转到hook页面
() => {
    router.push({
        name: 'hook'
    })
};
// store
import {
    useStore
} from 'vuex';
// Store
const store = useStore();
// 挂载
store.commit('increment');
// Count
const count = store.state.count;
// components
import HelloWorld from '@/components/HelloWorld.vue';
// env
console.log(import.meta.env);
// hot
console.log(import.meta.hot);
</script>
<style module="styles">
.blue{
    color:blue;
}
.red{
    color:red;
}
</style>
