# 超轻量级、多条件验证的辅助函数。

## start
``` js
Validator.hintFn =window.alert //Validator的输出 message 的提示函数

const v = new Validator([
  {
    fn: () => {
      return 1===1;//需要验证的表达式，需要返回布尔值，返回 true 时 表示验证通过
    },
    message: "姓名必填！"
  },
  {
    fn: () => {
      return  2===1;
    },
    message: "年龄必填！"
  },

])

v.then(res => {
  console.log('验证成功！');
})
```

## API
hintFn 函数类型 (选填)
- 静态方法,指定 `Validator`的输出 `message` 的提示函数,可选值为`window.alert`,`console.log`,默认值为`console.log`,也可使用第三方UI库的提示信息,例如`element-ui`的`this.$message;`

then 函数类型 (选填)
- 验证条件全部通过时需要执行的回调函数，
