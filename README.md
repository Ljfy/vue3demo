# test

### computed 计算属性 与vue2配置功能一致
```js
import {computed} from "vue"
setup(){
  // 计算属性简写
  let fullName = computed(()=>{
    return person.firstName + '-'+person.lastName
  })

  // 计算属性完整
    let fullName = computed({
        get(){
         return person.firstName + '-'+person.lastName
       },
       set(value){
         const nameArr = value.split('-')
         person.firstName = nameArr[0]
         person.lastName = nameArr[1]
       } 
    })
}
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
