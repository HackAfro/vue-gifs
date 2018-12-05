<template>

    <view class="container">
        <text class="type">{{gif.type}}</text>
        <image class="img" :source="{uri: `${gif.images.original.url}`}"
               style="max-width:100%;"/>
        <text class="title">{{titleCase(gif.title)}}</text>
    </view>

</template>

<script>
  export default {
    name: 'GifItem',
    props: ['gif'],
    methods: {
      titleCase(text) {
        const textArray = text.split(' ');
        return textArray.map(text => `${text[0].toUpperCase()}${text.slice(1)}`).join(' ');
      }
    }
  };
</script>

<style>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-bottom: 30px;
        position: relative;
    }

    .img {
        height: 200px;
        width: 300px;
    }

    .title {
        font-size: 14px;
        font-weight: 500;
        margin-top: 7px;
    }

    .type{
        position: absolute;
        top: 10px;
        background-color: darkgoldenrod;
        opacity: 0.8;
        padding-top: 6px;
        padding-bottom: 6px;
        padding-left: 10px;
        padding-right: 10px;
        text-align: center;
        font-size: 13px;
        font-weight: 500;
        color: white;
        z-index: 1;
        right: 40px;
        border-radius: 6px;
    }
</style>