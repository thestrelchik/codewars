# codewars
***
### Head, Tail, Init and Last
```
let head = x => x[0]  //стелочная функция, берём нулевой индекс
let tail = x => x.slice(1)  //отрезаем начиная с первого индекса до последнего
let init = x => x.slice(0, x.length-1)  //отрезаем  с нулевого до препоследнего индекса
let last = x => x[x.length-1]   //берем послений элемент массива
```
***
### Array Deep Count
```
function deepCount(a){
  let count = 0
  let r = a => {
    count = count + a.length; //длинна массива первого уровня
    for ( let i of a ) {
      if ( Array.isArray(i) ) { //проверка на массив
        r(i); // рекурсия с новым аргументом
      }
    }
  }
  r(a);
  return count;
}
deepCount([[[[[[[[[]]]]]]]]]) //8
```
*** 
### Run-length encoding
```
let runLengthEncoding = function(str){
  const arr=[];
  
  let value = 1;
  
  for (let i=0; i<str.length; i++){
      if (str[i]!==str[i+1]){
        
        arr.push([value,str[i]]);
        value=1;
      } else {
        value++;
      }
  }
  return arr;
}
```
*** 
### Duplicate Encoder
```
 function duplicateEncode(word) {
  return word
    .toLowerCase() //нижний регистр
    .split("") // разбить строку  на  массив букв
    .map(function (a, i, word) { // создает новый массив и передоет туда результаты функции
      if(word.indexOf(a) == word.lastIndexOf(a)) { // если текущеее в обходе значение равно последнему значению
        return "("
      } else {
        return ")"
      }
    })
    .join(""); //обеденить элементы в строку
}

```
