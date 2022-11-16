# Part4 YuchenWang Worked with KatrinaJi

---
# GIF of 2X Input with Duration of 5 sec



The output should be 10s



# GIF of 0.5X Output With Duration of 5 sec



The output should be 2.5 s

---

## Explain 

In this part we only need to add two functions at Python to achieve control the motion.

- `slow_motion`  funtion

```
def slow_motion(data_arrays):
    two_times_data = []
    for data in data_arrays:
        two_times_data.append(data)
        two_times_data.append(data)
    return two_times_data
```

This function inserts a same array to the orinal array with 1 bit position shift. For example, if I input 10, I will insert the bits as follwing next positions and it will become 1100. So, when my input rate is 1X and the duration is 5 seconds, my output is 0.5X and the duration will be 10 seconds.

---

- `up_motion` function

```
def up_motion(data_arrays):
    half_data = []
    for index in range(len(data_arrays)):
        if index % 2 == 0:
            half_data.append(data_arrays[index])
    return half_data
```

This function removes the odd or even bits of the entire record to halve the data. For example, if I input 1100, I will remove the bits on even positions and it will become 10. So, when my input rate is 1X and the duration is 5 seconds, my output is 2X and the duration will be 2.5 seconds.

