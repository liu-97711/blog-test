# JS函数的执行时机

```javascript
// 以下代码打印6个6 
let i = 0
for(i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}


/*
为什么会打印6个6
是因为setTimeout不会立即执行，当for循环结束之后才会执行，for循环执行完毕后，i的值已经变为了6，此时再去执行6次setTimeout，所以会打印出6个6
*/
```


```javascript
/*
让代码打印出0,1,2,3,4,5的方法
*/
//方法1
for(let i=0;i<6;i++){
  setTimeout(()=>console.log(i),0);
}

//i存在于for的块级作用域中，每次的i都被保留下来，所以执行setTimeout时总是取到当时的i



//方法2
//让setTimeout立即执行
for(var i=0;i<6;i++){
    (function(i){
        setTimeout(function(){
            console.log(i);
        },0)
    })(i)
}

//方法3
//实际上也是让他立即执行
function doSetTimeout(i) {
  setTimeout(function() { alert(i); }, 100);
}

for (var i = 1; i <= 2; ++i){
  doSetTimeout(i);
}

```
