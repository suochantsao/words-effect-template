<template>
  <div class="flex">
    <div class="w-50 title-align">
      <div class="btn-group">
        <p>文字效果</p>
        <el-button-group>
          <el-button type="primary" @click="resetEffect('effect1')">效果一</el-button>
          <el-button type="warning" @click="resetEffect('effect2')">效果二</el-button>
        </el-button-group>
      </div>
      <div class="btn-group">
        <p>文字對齊</p>
        <el-button-group>
          <el-button @click="resetAlign('left')">置左</el-button>
          <el-button @click="resetAlign('center')">置中</el-button>
          <el-button @click="resetAlign('right')">置右</el-button>
        </el-button-group>
      </div>
      <div class="input">
        <p class="description">請輸入文字</p>
        <el-input
          size="large"
          v-model="inputValue"
          style="width: 240px"
          placeholder="請輸入文字"
          clearable
        />
      </div>
      <p class="description">請選擇字體</p>
      <el-select
        v-model="fontFamilyValue"
        placeholder="請選擇字型"
        size="large"
        style="width: 240px"
        clearable
      >
        <el-option v-for="item in options" :key="item" :label="item" :value="item" />
      </el-select>
      <div class="colorPicker">
        <p>請選擇顏色</p>
        <el-color-picker v-model="colorValue" />
      </div>
      <div class="btn-group">
        <p>背景選擇</p>
        <el-button-group size="large">
          <el-button class="firstBg" @click="resetBg('bg1')">背景一</el-button>
          <el-button class="secBg" @click="resetBg('bg2')">背景二</el-button>
          <el-button class="thirdBg" @click="resetBg('bg3')">背景三</el-button>
        </el-button-group>
      </div>
    </div>
    <div
      class="resultBlock"
      :class="{
        effect1Block: effectValue === 'effect1',
        effect2Block: effectValue === 'effect2',
        firstBg: bgValue === 'bg1',
        secBg: bgValue === 'bg2',
        thirdBg: bgValue === 'bg3',
        alignRight: alignValue === 'right',
        alignCenter: alignValue === 'center',
        alignLeft: alignValue === 'left'
      }"
    >
      <p
        class="resultString str1"
        :style="{ color: colorValue, fontFamily: fontFamilyValue }"
        :class="{ effect1: effectValue === 'effect1', effect2: effectValue === 'effect2' }"
      >
        {{ inputValue }}
      </p>
      <p
        class="resultString str2"
        :style="{ color: colorValue, fontFamily: fontFamilyValue }"
        :class="{ effect1: effectValue === 'effect1', effect2: effectValue === 'effect2' }"
      >
        {{ inputValue }}
      </p>
      <p
        class="resultString str3"
        :style="{ color: colorValue, fontFamily: fontFamilyValue }"
        :class="{ effect1: effectValue === 'effect1', effect2: effectValue === 'effect2' }"
      >
        {{ inputValue }}
      </p>
    </div>
  </div>
</template>
<script setup>
import { ref } from 'vue'
const effectValue = ref('effect1')
const bgValue = ref('bg1')
const alignValue = ref('center')
const inputValue = ref('')
const fontFamilyValue = ref('')
const colorValue = ref()
const options = ref([
  'Inter',
  'Helvetica Neue',
  'Helvetica',
  'PingFang SC',
  'Hiragino Sans GB',
  'Microsoft YaHei',
  '微软雅黑',
  'Arial',
  'sans - serif'
])
const resetEffect = (effect) => {
  effectValue.value = effect
  colorValue.value = ''
}

const resetBg = (bg) => {
  bgValue.value = bg
}

const resetAlign = (align) => {
  alignValue.value = align
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Overlock:ital,wght@0,400;0,700;0,900;1,400;1,700;1,900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400..900&display=swap');
</style>
