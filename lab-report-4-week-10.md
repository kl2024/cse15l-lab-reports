# [Lab Report 4](https://kl2024.github.io/cse15l-lab-reports/lab-report-2-week-10.html)
---
## Finding Tests with Different Results

To be able to find the tests with varying results, I used `bash` scripting along with `vimdiff`. I used `echo $file` to print out the file name for each test case, and copied it over to the `script.sh` file with `cp`. I then ran the script using `bash` commands and used `vimdiff` on both the repositories.

## Test files with different results

Link to test files:
- [Test 22](https://github.com/nidhidhamnani/markdown-parser/blob/8dd87e6914ae40a4321aac8e2483e349de40b03c/test-files/22.md)
- [Test 194](https://github.com/nidhidhamnani/markdown-parser/blob/8dd87e6914ae40a4321aac8e2483e349de40b03c/test-files/194.md)

## Test 22

Using the [CommonMark demo](https://spec.commonmark.org/dingus/) site, the correct output should be `[/bar\* “ti\*tle”]`. 

Expected:
![image](https://user-images.githubusercontent.com/103288212/172572342-ea68e74f-c95e-4ce0-9c16-e163dcaa5945.png)


Actual:
![image](https://user-images.githubusercontent.com/103288212/172571016-38f016a4-32dd-4b9d-b316-ff6f7f11971f.png)


## Test 194

Using the [CommonMark demo](https://spec.commonmark.org/dingus/) site, the correct output should be `[url]`.

Expected:
![image](https://user-images.githubusercontent.com/103288212/172574314-5bc3e07e-5f6c-4c84-9e9c-5ba79dfdf5f6.png)


Actual:
![image](https://user-images.githubusercontent.com/103288212/172574457-7fd56895-a44f-47af-88e4-9a65c83fe4dc.png)


