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
### Length of missing array
```
function getLengthOfMissingArray(arr) {
  
  if (!Array.isArray(arr) || arr.length === 0) // проверка если не массив или пустой массив
      return 0;
  
  for (let i=0; i<arr.length; i++) { //проверка есть ли пустой подмасив
    if(arr[i]===null||arr[i].length===0){return 0}
  }
  arr.sort((a,b) => b.length-a.length) //сортируем подмасивы по убыванию длинны 
  
  for (let i = 0; i < arr.length - 1; i++) { // 0 < (5-1) 
      if (arr[i].length - arr[i + 1].length !== 1) //если текущую длинну подмасива отнять следующую длиину подмассива по убыванию +1
      return arr[i].length - 1;
  }
}

```
### Let's Recycle!
```
function recycle(arr) {
  let paper = []
  let glass = []
  let organic = []
  let plastic = []

  arr.forEach(typeKey => { //обходим массив и приминяем функцию для каждого элемента(объекта) массива 
    if(typeKey.material === 'paper' || typeKey.secondMaterial === 'paper' ) paper.push(typeKey.type) //если есть такой ключ -пушим значение ключа в соответствующий массив
    if(typeKey.material === 'glass' || typeKey.secondMaterial === 'glass') glass.push(typeKey.type)
    if(typeKey.material === 'organic' || typeKey.secondMaterial === 'organic') organic.push(typeKey.type)
    if(typeKey.material === 'plastic' || typeKey.secondMaterial === 'plastic') plastic.push(typeKey.type)
  });
  return [paper, glass, organic, plastic]
}

```
