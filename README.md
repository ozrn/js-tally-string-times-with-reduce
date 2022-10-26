# JS30# 18: js-tally-string-times-with-reduce
This is the eighteenth coding challenge of JS30 series by Wes Bos.<br><br>
In this practice, array map and reduce methods are used to calculate total runtime of given videos in hours, minutes and seconds.
### Array map method() 
It creates a new array by calling a function once for each element in an array. Here, in this practice, first, we need to convert our nodelist into a new array before using the method. After then, we map over the new array to get all seconds. Since all of them are in string formats, split and parseFloat methods are applied to find out the seconds as a number.
```const timeNodes = [...document.querySelectorAll("[data-time]")];
   const seconds = timeNodes
  .map(node => node.dataset.time)
  .map(timeCode=> {
   const [mins, secs] = timeCode.split(":").map(parseFloat); // convert string to number
    return (mins * 60) + secs ;
  }); 
  ```
### Array reduce method()
It returns a single value: the function's accumulated result. Here, we use this method to sum all seconds and finally get a single value.
```
const seconds = timeNodes
  .map(node => node.dataset.time)
  .map(timeCode=> {
    const [mins, secs] = timeCode.split(":").map(parseFloat); // convert string to number
    return (mins * 60) + secs ;
  }) 
.reduce((total, vidTotalSecs) => total + vidTotalSecs);
```
