# algorithm
前端算法题（每日训练+更新）

# 排序算法
### 冒泡排序（俩俩比较）
```javascript
// 小到大，
function bubbleSort (arr) {
    for(let i=0;i<arr.length-1;i++){
        for(let j=0;j<arr.length-i-1;j++){
            if(arr[j]>arr[j+1]){
                const temp = arr[j]
                arr[j] = arr[j+1]
                arr[j+1] = temp
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
### 