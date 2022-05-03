# [Lab Report 2](https://kl2024.github.io/cse15l-lab-reports/lab-report-2-week-4.html)
---
## Code change 1
![Image](https://user-images.githubusercontent.com/103288212/165167651-3211b043-a2e1-4b89-8d87-f1a1146411f3.png)

[View file](https://github.com/kl2024/markdown-parser/blob/main/test-file.md) to see failure-inducing input.

Symptom Output:
![Image](https://user-images.githubusercontent.com/103288212/166409881-454819ad-f0ad-448e-8011-a9c1cc6548e4.png)

This error was due to the file having an extra line at the end of the code. Upon compiling, the program would then run into an issue of an infinite loop. By adding a `print` statement of the current index, we were able to debug the errors and rid the extra line to solve this issue.

## Code change 2
![Image](https://user-images.githubusercontent.com/103288212/165168309-dc5de2ec-e891-46df-9d8c-224089014798.png)

[View file](https://github.com/kl2024/markdown-parser/blob/main/test-file2.md) to see failure-inducing input.

Symptom Output:
![Image](https://user-images.githubusercontent.com/103288212/166410002-bc38167b-c4a0-442a-8d47-a27246817451.png)


This error was due to there being a large space between the `[]` brackets and `()` parentheses for the `file.md` links which would make us run into a Java heap space error. To solve this issue, we added an `if` statement that checks if the closing bracket is followed by the open parenthesis, and skips to the index of the open parenthesis to close the gap if not.


## Code change 3
![Image](https://user-images.githubusercontent.com/103288212/165168407-354afdad-7744-439d-a76c-b0043c0c0531.png)

[View file](https://github.com/kl2024/markdown-parser/blob/main/test-file3.md) to see failure-inducing input.

Symptom Output:
![Image](https://user-images.githubusercontent.com/103288212/166410107-adeeaa95-fa12-42b8-bdd0-d94bf3a727c8.png)


This error was due to not importing the necessary interfaces to successfully run our program. Upon compiling, the program would then run `illegal start of expression` and `cannot find symbol` errors. By correctly importing the ArrayList and List interfaces, we were able to solve this issue.
