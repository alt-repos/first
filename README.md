**Q27 (Sayak)** <br>
Rohit wrote a code to evaluate the value of a mathematical expression. However, the code turned out to be wrong. Given the following inputs, write the output of this code. Also explain where Rohit went wrong in at most two sentences. Note that you do not need to give a modification, just point out the error. <br>

The variable “eqn” is a string. When we pass strings into a function, we need pointers, which you will learn later in this course. For now, think of “eqn” and “\*eqn” as arrays, and the eqn[i] gives us the (i+1)-th character, as is the case with usual arrays you are familiar with.<br>

```
#include<stdio.h>
#include<stdlib.h>

int func1(char c) { return (c >= '0' && c <= '9'); }
int func2(char c) { return (c - '1'); }
int evaluate(char *eqn)
{
    if (*eqn == '\0')  return -1;
    int val = func2(eqn[0]);
    for (int i = 1; eqn[i]; i += 2)
    {
        char opr = eqn[i], opd = eqn[i+1];
        if (!func1(opd))  return -1;
        if (opr == '+')       val += func2(opd);
        else if (opr == '-')  val -= func2(opd);
        else if (opr == '*')  val *= func2(opd);
        else if (opr == '/')  val /= func2(opd);
        else                  return -1;
    }
    return val;
}
int main()
{
    char eqn[500];
    scanf("%s", eqn);
    int val = evaluate(eqn);
    (val == -1)? printf("%s is Invalid", eqn):
                 printf("Value of %s is %d", eqn, val);
	return 0;
}
```
Write the outputs according to the given inputs:
1. <p align='right'>2 Marks</p>
   ```C
 	Input: 3+7/3+5
   ```
`Output: Value of 3+7/3+5 is 8`

2. <p align='right'>2 Marks</p>
   ```C
 	Input: 5+4*2/8    
   ```
  `Output: Value of 5+4*2/8 is 1`
  
3. <p align='right'>2 Marks</p>
   ```C
 	Input: 9+6/4*3  
   ```
  `Output: Value of 9+6/4*3 is 8`
  
4. <p align='right'>2 Marks</p>
   ```C
 	Input: 4++1       
   ```
  `Output: 4++1 is Invalid`
<br><br>

Write your explanations which resulted in the code being erroneous:
```C


```
- `Line 5: It should be (c - ‘0’) instead of (c-’1’).` <p align='right'>0.5 Mark</p>
- `Line 16, 17: Dividing/multiplying by entire value obtained until now.` <p align='right'>1.5 Marks</p>




**Q28 (Sayak)**








