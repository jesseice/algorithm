# algorithm
前端算法题（每日训练+更新）

# 排序算法（参考https://segmentfault.com/a/1190000020072884）
### 冒泡排序（俩俩比较）
```javascript
// 小到大
function bubbleSort (arr) {
    for(let i=0;i<arr.length-1;i++){
        for(let j=0;j<arr.length-i-1;j++){
            if(arr[j]>arr[j+1]){
                [arr[j],arr[j+1]] = [arr[j+1],arr[j]]
            }
        }
    }
    return arr
}
```  
### 选择排序（以最小（大）的一个元素对剩余的数组元素做比较，得到最小（大）的元素）
```javascript
// 小到大
function selectionSort(arr){
    for(let i=0;i<arr.length-1;i++){
        let min = i
        for(let j=i+1;j<arr.length;j++){
            if(arr[min]>arr[j]){
                min = j
            }
        }
        let temp = arr[i]
        arr[i] = arr[min]
        arr[min] = temp
    }
    return arr
}
```  
### 插入排序
```javascript
//小到大,思路：分为俩部分，一部分是排序好的，一部分是未排序。先把数组第一个元素当成已经排序好的，然后拿第二个元素去比较，第一个>第二个，就二一换位，依此类推
function insertionSort(arr){
    for(let i=1;i<arr.length;i++){
        let preIndex = i-1
        let current = arr[i]
        while(preIndex>=0&&arr[preIndex]>current){
            arr[preIndex+1] = arr[preIndex]
            preIndex--
        }
        arr[preIndex+1] = current
    }
    return arr
}
```
### 快速排序
```javascript
//小到大,思路：分为俩部分，一部分是排序好的，一部分是未排序。先把数组第一个元素当成已经排序好的，然后拿第二个元素去比较，第一个>第二个，就二一换位，依此类推
function quickSort(arr, left, right) {
    var len = arr.length,
        partitionIndex,
        left =typeof left !='number' ? 0 : left,
        right =typeof right !='number' ? len - 1 : right;
 
    if (left < right) {
        partitionIndex = partition(arr, left, right);
        quickSort(arr, left, partitionIndex-1);
        quickSort(arr, partitionIndex+1, right);
    }
    return arr;
}
 
function partition(arr, left ,right) {    // 分区操作
    var pivot = left,                     // 设定基准值（pivot）
        index = pivot + 1;
    for (var i = index; i <= right; i++) {
        if (arr[i] < arr[pivot]) {
            swap(arr, i, index);
            index++;
        }       
    }
    swap(arr, pivot, index - 1);
    return index-1;
}
 
function swap(arr, i, j) {
    var temp = arr[i];
    arr[i] = arr[j];
    arr[j] = temp;
}
```
var a = 0;
(function () {
  var a = { a: 0 };
  var b = function () {
    setTimeout(() => {
      console.log(this.a)
    })
  }
  b();
  b.call(a);
  a.a = 1;
  console.log(a);
  a = { a: 2 }
  console.log(a.a)
})()