# citySelect

> 中国省市县联动

## use

### vue

```vue
<template>
  <div id="app">
    <select v-model="provinceIndex" placeholder="请选择">
      <option
        v-for="(item, index) in provinceOptions"
        :key="index"
        :label="item"
        :value="index">
      </option>
    </select>

    <select v-model="cityIndex" placeholder="请选择">
      <option
        v-for="(item, index) in cityOptions(provinceIndex)"
        :key="index"
        :label="item"
        :value="index">
      </option>
    </select>

    <select v-model="countryIndex" placeholder="请选择">
      <option
        v-for="(item, index) in countryOptions(provinceIndex, cityIndex)"
        :key="index"
        :label="item"
        :value="index">
      </option>
    </select>
  </div>
</template>

<script>
import {
  provinceOptions,
  cityOptions,
  countryOptions
} from 'cn-city-select-options'

export default {
  name: 'App',

  data () {
    return {
      provinceIndex: 0,
      provinceOptions,

      cityOptions,
      cityIndex: 0,

      countryOptions,
      countryIndex: 0
    }
  }
}
</script>

```