# uniapp-modal

多种类型的modal，覆盖原生导航栏

## 使用方式

**在main.js中**  

~~~
// 注册全局modal组件
import chunLeiModal from '@/components/chunLei-modal/chunLei-modal.vue'
Vue.component('chunLei-modal',chunLeiModal);
~~~

**在index.vue中**  

~~~
<template>
	<view class="content">
		<chunLei-modal v-model="value" :mData="data" :type="type" @onConfirm="onConfirm" @onCancel="onCancel" navMask>
		</chunLei-modal>
	</view>
</template>
~~~

## 事件

| 事件名 | 说明 |
| ---  | --- |
| confirm | 用户点击了确定按钮 |
| cancel | 用户点击了取消按钮 |
