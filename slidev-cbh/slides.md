---
theme: seriph
drawings:
  persist: true
---

# 认识后端

---

# 前端、后端、WEB


---

# 前后端交互方式的演进

---

## 来看一段代码

```js
class Watcher {
  constructor(vm, expOrFn, cb) {
    this.vm = vm;
    // 执行 this.getter() 就可以读取到内容
    this.getter = parsePath(expOrFn);
    this.cb = cb;
    this.value = this.get();
  }
  get() {
    window.target = this;
    let value = this.getter.call(this.vm, this.vm);
    window.target = undefined;
    return value;
  }
  update() {
    const oldValue = this.value;
    this.value = this.get();
    this.cb.call(this.vm, this.value, oldValue);
  }
}
```

记笔记啦


---

下面看一个 div

<div id="box"></div>

<style>
  #box {
    width: 200px;
    height: 200px;
    background-color: green;
    border: 5px solid red;
  }
</style>
