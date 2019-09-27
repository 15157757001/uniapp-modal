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

## OBJECT参数说明

| 参数 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| type | String | default | modal类型：default，select，advert，share，input，custom |
| value | Boolean | false | 是否显示 |
| maskEnable | Boolean | true | 是否点击遮罩退出 |
| mData | Object, Array | Object | 数据 |
| navMask | Boolean | 否 | 是否遮住导航栏 |
| nav | Boolean | true | 该页面是否有导航栏，存在时遮住 |

## 事件

| 事件名 | 说明 |
| ---  | --- |
| confirm | 用户点击了确定按钮 |
| cancel | 用户点击了取消按钮 |
