import time

import random

def merge_sort(alist, start, end):

 '''Sorts the list from indexes start to end - 1 inclusive.'''

 if end - start > 1:

 mid = (start + end)//2

 merge_sort(alist, start, mid)

 merge_sort(alist, mid, end)

 merge_list(alist, start, mid, end)

def merge_list(alist, start, mid, end):

 left = alist[start:mid]

 right = alist[mid:end]

 k = start

 i = 0

 j = 0

 while (start + i < mid and mid + j < end):

 if (left[i] <= right[j]):

 alist[k] = left[i]

 i = i + 1

 else:

 alist[k] = right[j]

 j = j + 1

 k = k + 1

 if start + i < mid:

 while k < end:

 alist[k] = left[i]

 i = i + 1

 k = k + 1

 else:

 while k < end:

 alist[k] = right[j]

 j = j + 1

 k = k + 1

alist = random.sample(range(1, 1000000), 5000)

print(alist)

start_time = time.time()

merge_sort(alist, 0, len(alist))

end_time = time.time()

print('Sorted list: ', end='')

print(alist)

print('time taken for sorting is:',(end_time-start_time))# ADa
