# Object
## 静态属性

### defineProperty
```js
    // @params {obj} 定义属性的对象
    // @params {prop} 定义或修改的属性名称 或 Symbol
    // @params {descriptor} 定义或修改的属性描述符
    Object.defineProperty(obj, prop, descriptor);
```

#### 数据描述符
+ value
+ writable (default: fasle)

#### 存取描述符
+ getter
+ setter

#### 描述符共享属性
+ configurable (default: false; 为true时代表该属性可以被修改和重复定义)
+ enumerable (default: false;)

---

## tips:
+ 所创建描述符对象选项不一定都是自身属性，可能会有继承来的属性。

```js
    // 解决办法
    const descriptor = Object.create(null);
    // 或冻结当前对象
    const descriptor = Object.freeze({})
```
