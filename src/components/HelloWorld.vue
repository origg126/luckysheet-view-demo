<template>
  <div class="hello">
    <div
      id="luckysheet"
      style="margin:0px;padding:0px;position:absolute;width:100%;height:100%;left: 0px;top: 0px;"
    ></div>
  </div>
</template>

<script>
// 初始化定义数据
let data1 = [
    {
        "r": 0,
        "c": 0,
        "v": "hahaha"
    },
    {
      "r": 0,
      "c": 1,
      "v": 1
    },
    {
      "r": 1,
      "c": 1,
      "v": 2
    },
    {
        "r": 2,
        "c": 1,
        "v": {
            "f": "=SUM(B1:B2)",
            "bg": "#fff000",
            "v": "3",
            "m": "3"
        }
    },
    { 
        "r": 0,
        "c": 2,
        "v": "value 2"
    }
];
//初始化sheet
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted() {
    // In some cases, you need to use $nextTick
    // this.$nextTick(() => {
          $(function () {
            luckysheet.create({
              container: "luckysheet",
              lang: 'zh',
              // sheet页，celldata为数据内容
              data: [
                { "name": "SheetName 自定义", "celldata": data1, "index": 0 }, 
                { "name": "Sheet2", "data": [], "index": 1}]
            });
          });
      
    // });
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
