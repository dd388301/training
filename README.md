#include <stdio.h>
int main() {
   int r, c, num, middle;
   printf("Enter the number of rows and columns: ");
   scanf("%d %d", &r, &c);  
   int arr[r][c];
   printf("Enter the elements of the 2-D matrix: ");
   for(int i = 0; i < r; i++) {
       for(int j = 0; j < c; j++) {
           scanf("%d", &arr[i][j]);
       }
   }
  printf("Enter the search number: ");
   scanf("%d", &num);  
     int left = 0, right = r * c - 1, flag = 0;
     while (left <= right) {
       middle = (left + right) / 2;
       int midRow = middle / c;
       int midCol = middle % c;
              if (arr[midRow][midCol] == num) {
           printf("Search element is found at position (%d, %d)\n", midRow, midCol);
           flag = 1;
           break;
       }
       else if (arr[midRow][midCol] > num) {
           right = middle - 1;
       }
       else {
           left = middle + 1;
       }
   }
      if (flag == 0) {
       printf("Search element is not found\n");
   }
      return 0;
}
