How to Replace a Substring in a String
Replace a Substring in a String is one of the complicated operations that is performed on a string, for doing this, we will be asking the user to input a base string, than we will ask for a substring which is to replaced, and finally we will ask for the string which is to be placed on the place of substring, there a few exceptions also with which we have to deal, before replacing the substring, like, what is the substring entered by the user, doesn’t exist in the base string, in that case we will output a simple message, that please enter a correct substring.

Replace a Substring in a String using C Language
Algorithm to Replace string in C
Start
Accept the main string
Accept the sub-string
Accept the string, with which to replace the sub-string.
Check if the substring is present in the main string or not
If the substring is not present in the main string, terminate the program.
If the substring is present in the main string then continue.
Iterate each character of the main string
Replace the sub-string with the input string.
Print the new string.
While loop in C
C Code for replacing a substring in a string
#include<stdio.h>  
#include<string.h>  
  int main() {
        char str[256] = "prepinsta", substr[128] = "insta", replace[128] = "ster ", output[256];
        int i = 0, j = 0, flag = 0, start = 0;
        
        str[strlen(str) - 1] = '\0';
        substr[strlen(substr) - 1] = '\0';
        replace[strlen(replace) - 1] =  '\0';

        // check whether the substring to be replaced is present 
        while (str[i] != '\0')
        {
                if (str[i] == substr[j]) 
                {
                        if (!flag)
                                start = i;
                        j++;
                        if (substr[j] == '\0')
                                break;
                        flag = 1;
                } 
                else 
                {
                        flag = start = j = 0;
                }
                i++;
        }
        if (substr[j] == '\0' && flag)
        {
                for (i = 0; i < start; i++)
                        output[i] = str[i];

                // replace substring with another string 
                for (j = 0; j < strlen(replace); j++) 
                {
                        output[i] = replace[j];
                        i++;
                }
                // copy remaining portion of the input string "str" 
                for (j = start + strlen(substr); j < strlen(str); j++)
                {
                        output[i] = str[j];
                        i++;
                }
                // print the final string 
                output[i] = '\0';
                printf("Output: %s\n", output);
        } else {
                printf("%s is not a substring of %s\n", substr, str);
        }
        return 0;
  }
Output
Output: 
prepster
Note
The time complexity of the above code is O(n) as we are iterating over the string once.
