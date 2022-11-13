# merge_sort_py


````py
class Solution:
    def merge(self,arr, l, m, r): 
        # code here 
        L = arr[l:m+1] # new array L
        R = arr[m+1:r+1] # new array R
        i = j = 0
        k = l
        while i < len(L) and  j < len(R):
            if L[i] <= R[j]:
                arr[k] = L[i]
                i+= 1
            else: 
                arr[k] = R[j]
                j+= 1
            k+= 1 
                
        while i < len(L): # remaining array elements if any
            arr[k] = L[i]
            i+= 1
            k+= 1
            
        while j < len(R): # remaining array elements if any
            arr[k] = R[j]
            j+= 1
            k+= 1
            
    def mergeSort(self,arr, l, r):
        #code here
        if l<r: 
            # mi = l + ( l - r ) // 2
            mi = ( l + r ) // 2
            self.mergeSort(arr, l, mi)
            self.mergeSort(arr, mi+1, r)
            self.merge(arr, l, mi, r)
        return arr

# Geek
````
