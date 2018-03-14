# 4. R

```
How to make professional and beautiful plots
```


    > **Tips:**  
    > Things can be done with multiple ways  
    > Efficient Programming : Bash > R > Perl/Python > Excel > C/C++

    ### 1\) Examples

    #### Example I. mean and t test

    ---

    ```
    sh# R
     x<-read.table("foo1")
     y<-read.table("foo2") 
     mean(x) 
     mean(y) 
     ?t.test 
     t.test( x,y,alternative=c("greater") )
    ```

    Or write this into a file, script.R, then






