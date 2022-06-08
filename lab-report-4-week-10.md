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
![image](https://user-images.githubusercontent.com/103288212/172571623-6a0fd5ae-88aa-45cc-b425-3f31f68541fd.png)

Actual:
![image](https://user-images.githubusercontent.com/103288212/172571016-38f016a4-32dd-4b9d-b316-ff6f7f11971f.png)


## Test 194

According to the [CommonMark demo](https://spec.commonmark.org/dingus/) the correct output should be `[url]`.
