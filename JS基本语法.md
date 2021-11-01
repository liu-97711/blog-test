# JS基本语法

* 表达式和语句
  
  语句（statement）是为了完成某种任务而进行的操作
  
  表达式（expression）指一个为了得到返回值的计算式
  
  句和表达式的区别在于，前者主要为了进行某种操作，一般情况下不需要返回值；后者则是为了得到返回值，一定会返回一个值。
  
 * 标识符的规则
 
   标识符（identifier）指的是用来识别各种值的合法名称
   
   第一个字符，可以是任意 Unicode 字母（包括英文字母和其他语言的字母），以及美元符号 $ 和下划线 _
   
   第二个字符及后面的字符，除了 Unicode 字母、美元符号和下划线，还可以用数字0-9
   
 * if else 语句

   ```javascript
   var a = 1;
   if(a === 2){
    console.log("条件满足");
   }else{
    console.log("条件不满足");
   }
   
   //对一个变量进行多次判断时，多个语句可以连写在一起
   var a = 1;
   if(a === 2){
    console.log(2);
   }else if(a === 3){
    console.log(3);
   }else if(a === 4){
    console.log(4);
   }else{
    console.log(5);
   }
   ```
 * while、for 语句

   while
   ```javascript
   var a = 0  //初始化                 
   while(a < 10){ //判断条件
     console.log(a);  //执行体
     a = a + 1; //递增表达式
   }
   
   var i = 0.1;
   while(!a===1){
    console.log(a);
    a = a + 0.1;
   }
   /*
   以上代码会进入死循环，因为浮点数的原因，a的值不可能严格等于1
   */
   ```
   
   for
   ```javascript
   for(初始化表达式;条件;递增表达式){  //初始化表达式（initialize）：确定循环变量的初始值，只在循环开始时执行一次。
    执行体;                          //条件表达式（test）：每轮循环开始时，都要执行这个条件表达式，只有值为真，才继续进行循环。
   }                                //递增表达式（increment）：每轮循环的最后一个操作，通常用来递增循环变量。
   
   for(var i=0;i<5;i++){
    setTimeout(()=>{},0)
   }  //以上代码的输出结果为输出5次5  因为setTimeout每次都是过一段时间后执行执行 导致的结果是先执行for这时i已经为5,再执行console,重复5次。
   ```
   
  * break 和 continue
    
    break语句用于跳出代码块或循环
    
    continue语句用于立即终止本轮循环，返回循环结构的头部，开始下一轮循环
    
    如果存在多重循环，不带参数的break语句和continue语句都只针对最内层循环
    
    ```javascript
    for(var a=0;a<10;a++){
      if(a%2 === 1){
        console.log(a);
        break;
      }
    } // 输出结果为1
    
    for(var a=0;a<10;a++){
      if(a%2 === 1){
        continue;
      }else{
        console.log(a);
      }
    } //0 2 4 6 8
    ```
    
  * label(标签)
    JavaScript 语言允许，语句的前面有标签（label），相当于定位符，用于跳转到程序的任意位置，标签的格式如下
    ```
    label:
    语句
    ```
    
    标签通常与break语句和continue语句配合使用，跳出特定的循环。
    ```
    top:
    for (var i = 0; i < 3; i++){
      for (var j = 0; j < 3; j++){
        if (i === 1 && j === 1) break top;
        console.log('i=' + i + ', j=' + j);
      }
    }
    // i=0, j=0
    // i=0, j=1
    // i=0, j=2
    // i=1, j=0
    ```
    
    ```
    top:
      for (var i = 0; i < 3; i++){
        for (var j = 0; j < 3; j++){
          if (i === 1 && j === 1) continue top;
          console.log('i=' + i + ', j=' + j);
        }
    }
    // i=0, j=0
    // i=0, j=1
    // i=0, j=2
    // i=1, j=0
    // i=2, j=0
    // i=2, j=1
    // i=2, j=2
    ```
    
    标签也可以用于跳出代码块。
    ```
    foo: {
      console.log(1);
      break foo;
      console.log('本行不会输出');
    }
    console.log(2);
    // 1
    // 2
    ```
