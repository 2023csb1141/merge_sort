# quick_sort

# Program to o sort a list of numbers using the quick sort technique

# Creation of an unsorted random list
import random

def list_crtr(a,b) :                               #a is the length of list and b is the range of numbers
    L=[]                                           #L is the list
    for i in range(a) :                            #i is the index of list
        L.append(random.randint(0,b))              #random numbers are appended to the list
    return L                                       #returning the list


# Making a function to sort the list using quick sort technique

# Merging the list
def merge(a,b) :                                    #a and b are the lists to be merged
    c=[]                                            #c is the merged list
    for i in range(len(a)) :                        #i is the index of list a
        c.append(a[i])                              #appending the elements of list a to list c
    for i in range(len(b)) :                        #i is the index of list b
        c.append(b[i])                              #appending the elements of list b to list c
    return c                                        #returning the merged list

# Quick sort function
def quick_sort(l) :                                 #l is the list to be sorted
    if len(l)==1 :                                  #if the length of list is 1
        return l                                    #returning the list
    else :                                         #if the length of list is greater than 1
        a= l[0]                                         #a is the first element of list l
        l1=[]                                           #l1 is the list of elements less than a
        l2=[]                                           #l2 is the list of elements greater than a
        for i in range(1,len(l)) :                      #i is the index of list l
            if l[i]<a :                                 #if element is less than a
                l1.append(l[i])                         #appending the element to list l1
            elif l[i]==a :                              #if element is equal to a
                continue                                #continuing the loop
            else :                                      #if element is greater than a
                l2.append(l[i])                         #appending the element to list l2
        l1.append(a*l.count(a))                         #appending the element a to list li
        l1=quick_sort(l1)                               #sorting the list l1
        l2=quick_sort(l2)                               #sorting the list l2
        l=merge(l1,l2)                                  #merging the lists l1 and l2
        return l                                        #returning the sorted list
def main() :
    k=eval(input("Enter the length of list- "))        #k is the length of list
    l= list_crtr(k,k*10)                                  #l is the list with k elements each in the range 0 to k*10
    print(l,"\n")                                           #printing the list
    print(quick_sort(l))                                    #printing the sorted list

main()
