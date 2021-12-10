# SUM-OF-AN-ARRAY
Write a program to find all pairs in array of integer whose sum is equal to a given  number

#include <stdio.h>
#define ARRAY_SIZE 100000
 
void hasSumPair(int array[], int size, int sum) {
  int i;
  
  int table[ARRAY_SIZE] = {0};
 
  for (i = 0; i < size; i++) {
      if(table[sum-array[i]] == 1 && sum-array[i] >= 0) {
          printf("Found Pair : %d %d\n", array[i], sum-array[i]);
      }
      table[array[i]] = 1;
  }
}
 
int main(){
    int i, array[1000], count, sum;
    printf("Enter the number of elements in Array\n");
    scanf("%d", &count);
     
    printf("Enter %d numbers\n", count);
    for(i = 0; i < count; i++){
        scanf("%d", &array[i]);
    } 
  
    printf("Enter the value of sum\n");
    scanf("%d", &sum);
  
    hasSumPair(array, count, sum);
 
    return 0;
}

==================================================================

OUTPUT 

----------------

Enter the number of elements in Array
6
Enter 6 numbers
1 2 3 4 5 6
Enter the value of sum
10
Found Pair : 6 4
