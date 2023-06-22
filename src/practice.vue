<template>
    <div>
        <div @click.once="innerClickHandler">外部
            <button class="box" @click="buttonClickHandler">内部</button>

        </div>
        <form @submit.prevent="submitHandler">
            <input type="text" v-model="inputValue">
            <button type="submit">Submit</button>
        </form>

    </div>
    <div class="box2">
        <ul>
            <li>1</li>
            <li>1</li>
            <li>1</li>
            <li>1</li>
            <li>1</li>
            <li>1</li>
            <li>1</li>
            <li>1</li>
            <li>1</li>
            <li>1</li>
            <li>1</li>
            <li>1</li>
        </ul>
        <div class="box3">
            <span>2</span>
            <span>2</span>
            <span>2</span>

        </div>
    </div>
</template>

<script setup>
const inputValue = ''
/**
 * .stop 阻止事件冒泡
 * prevent阻止页面重新加载
 * capture 事件冒泡时，改变事件的执行顺序，从外到内执行
 * once 保证事件只会执行一次
 */
const innerClickHandler = () => {
    console.log('外部');
}
const buttonClickHandler = () => {
    console.log('内部');
}
const submitHandler = () => {
    console.log('提交表单');
}
</script>
<style lang="scss" scoped>
.box2 {
    width: 300px;
    height: 200px;
    border: 1px solid skyblue;
    margin: auto;

    .box3 {
        height: 100px;
        display: flex;
        flex-direction: column;
        justify-content: space-around;

        span {
            width: 30px;
            height: 30px;
            background: pink;
            display: flex;
            justify-content: center;
            align-items: center;
        }
    }

    ul {
        margin: 0;
        padding: 0;
        width: 100%;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;

        li {
            text-align: center;
            list-style: none;
            width: 20%;
            line-height: 30px;
            border: 1px solid pink;

        }
    }
}
</style>