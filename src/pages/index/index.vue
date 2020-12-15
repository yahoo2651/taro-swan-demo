<template>
  <view class="index">
    <image
      src="https://cdn.jsdelivr.net/gh/fjc0k/placekitten/images/100/100.jpg"
    />
    <view> 姓名 </view>
    <input
      :value="name"
      type="text"
      placeholder="请输入姓名"
      @input="change1"
    />

    <view>性别</view>
    <view class="selector">
      <view
        v-for="item in genderOptions"
        :key="item.value"
        class="selector__item"
        :class="{ active: item.value === gender }"
        @tap="tap(item)"
      >
        {{ item.label }}
      </view>
    </view>
  </view>
</template>

<script>
import "./index.scss";

export default {
  data() {
    return {
      name1: "",
      name: "",
      gender: 1,
      gender2: "",
      genderOptions: [
        { label: "男", value: 1 },
        { label: "女", value: 2 },
      ],
    };
  },
  methods: {
    change(value) {
      console.error(value);
    },
    change1(e) {
      this.name1 = e.detail.value;
    },
    tap(item) {
      console.error({ item });
      this.gender = item.value;
      console.error(this.$data);
    },
    tap2(item) {
      setTimeout(() => {
        // this.gender2 = item.value;
        // this.$$forceUpdate();
        console.error("after", this.name1);
      }, 10);
      // console.error(this);
      // this.$forceUpdate();
      // let temp = this.name1;
      // this.name1 = "";
      // setTimeout(() => {
      //   this.name1 = temp;
      // });
    },
  },
};
</script>
