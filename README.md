# solution-assigmnet3.1-session3
DATA ANALYTICS WITH R, EXCEL &amp; TABLEAU
1. Define an m x n matrix of zeros and then enters a nested-for loop to fill the locations of the matrix, only if the two indexes differ. 
• The purpose is to create a lower triangular matrix, that is a matrix whose elements below the main diagonal are non-zero, the others are left untouched to their initialized zero value. 
• When the indexes are equal (if condition in the inner loop, which runs over j, the column index), a break is executed and the innermost loop is interrupted with a direct jump to the instruction following the inner loop, which is a print; then control gets to the outer for condition (over the rows, index i), which is evaluated again. 
• If the indexes differ, the assignment is performed and the counter is incremented by 1. 
• At the end, the program prints the counter ctr, which contains the #number of elements that were assigned. 

ANS .

> # make a lower triangular matrix (zeroes in upper right corner)
    > m=10; n=10;
    > ctr=0;   # used to count the assignemnt
    > mymat = matrix(0,m,n) # create a 10 x 10 matrix with zeroes 
    > for(i in 1:m) {
        +   for(j in 1:n) 
            +   {   
                +     if(i==j) 
                    +     { 
                        +       break;
                        +     } else 
                            +       {
                                +       mymat[i,j] = i*j   # we assign the values only when i<>j
                                +       ctr=ctr+1
                                +       }
                +   }
        +   print(i*j) 
        + }
    [1] 1
    [1] 4
    [1] 9
    [1] 16
    [1] 25
    [1] 36
    [1] 49
    [1] 64
    [1] 81
    [1] 100
    > print(ctr)  # print how many matrix cells were assigned
    [1] 45
  
    > mymat
    [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
    [1,]    0    0    0    0    0    0    0    0    0     0
    [2,]    2    0    0    0    0    0    0    0    0     0
    [3,]    3    6    0    0    0    0    0    0    0     0
    [4,]    4    8   12    0    0    0    0    0    0     0
    [5,]    5   10   15   20    0    0    0    0    0     0
    [6,]    6   12   18   24   30    0    0    0    0     0
    [7,]    7   14   21   28   35   42    0    0    0     0
    [8,]    8   16   24   32   40   48   56    0    0     0
    [9,]    9   18   27   36   45   54   63   72    0     0
    [10,]   10   20   30   40   50   60   70   80   90     0



b=matrix(0, sqrt(10)+1,sqrt(10)+1)
> b[lower.tri(b)| row(b)==col(b)] <- 1:10
> b
     [,1] [,2] [,3] [,4]
[1,]    1    0    0    0
[2,]    2    5    0    0
[3,]    3    6    8    0
[4,]    4    7    9   10


