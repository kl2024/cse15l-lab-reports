# [Lab Report 4](https://kl2024.github.io/cse15l-lab-reports/lab-report-4-week-10.html)
---
## Finding Tests with Different Results

To be able to find the tests with varying results, I used `bash` scripting along with `vimdiff`. I used `echo $file` to print out the file name for each test case, and copied it over to the `script.sh` file with `cp`. I then ran the script using `bash` commands and used `vimdiff` on both the repositories.

`MarkdownParse.java` on original CSE 15L repository from nidhidhamnani vs. my repository:
![image](https://user-images.githubusercontent.com/103288212/173178748-8c3426e2-4635-4589-be64-42a122211370.png)


## Test files with different results

Link to test files:
- [Test 22](https://github.com/nidhidhamnani/markdown-parser/blob/8dd87e6914ae40a4321aac8e2483e349de40b03c/test-files/22.md)
- [Test 194](https://github.com/nidhidhamnani/markdown-parser/blob/8dd87e6914ae40a4321aac8e2483e349de40b03c/test-files/194.md)

## Test 22

Results (cloned repository on the left and my repository on the right):
![image](https://user-images.githubusercontent.com/103288212/173179209-48ee9571-2d5e-4b80-9cef-bb530386f564.png)


Using the [CommonMark demo](https://spec.commonmark.org/dingus/) site, the correct output should be `[/bar\* “ti\*tle”]`. 

Expected:
![image](https://user-images.githubusercontent.com/103288212/172572342-ea68e74f-c95e-4ce0-9c16-e163dcaa5945.png)


Actual:
![image](https://user-images.githubusercontent.com/103288212/172571016-38f016a4-32dd-4b9d-b316-ff6f7f11971f.png)

This bug occurs because in the original cloned repository, links aren't recognized if there is a space within the brackts. Typically, we wouldn't have a space within our links either, but because of the presence of `\*` which essentially acts like a space, we run into the issue. We can try to fix this issue by checking the characters that come after the `\` to determine whether there are regex symbols or not.

![image](https://user-images.githubusercontent.com/103288212/173179142-b752de45-2657-4146-bf9a-a7b29e984aa1.png)


## Test 194
Results (cloned repository on the left and my repository on the right):
![image](https://user-images.githubusercontent.com/103288212/173179250-286a6c69-7830-42f0-a2df-be1fd3b9935d.png)



Using the [CommonMark demo](https://spec.commonmark.org/dingus/) site, the correct output should be `[url]`.

Expected:
![image](https://user-images.githubusercontent.com/103288212/172575164-0aa185b6-34a7-4e5a-bd54-b4ae202c6f2f.png)


Actual:
![image](https://user-images.githubusercontent.com/103288212/172574654-6fcbccdc-d813-43c2-a5bd-3d62030224d0.png)

This bug occurs within my repository (but not the cloned repository) likely because of self-reference links where something can be created into a link to a section by adding `[]:`. A possible fix could be to add an array storing words within `[]` if it is followed by a `:`, and then checking to see if valid text follows the `:`. If the word appears again within the document, we can compare it with the array to check if it already exists and skip the additional checks for links.

![image](https://user-images.githubusercontent.com/103288212/173179428-15e4f758-fc22-4188-88d5-50aade7b1c7a.png)



