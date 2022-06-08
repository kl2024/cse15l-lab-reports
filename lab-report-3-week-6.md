# [Lab Report 3](https://kl2024.github.io/cse15l-lab-reports/lab-report-2-week-6.html)
---
## Streamlining ssh Configuration

Here is the `.ssh/config` file:

![Image](https://user-images.githubusercontent.com/103288212/168501433-fb0236c6-6a5a-4ad9-b359-8f4551f7ceee.png)

Here is the `ssh` command of my login:

![Image](https://user-images.githubusercontent.com/103288212/168501512-4c37be74-07f5-496f-9692-763395196270.png)

Here is the `scp` command copying a file to my account:

![Image](https://user-images.githubusercontent.com/103288212/168501956-b28ae40e-2ec9-47dd-bd27-f011a05cc77e.png)
![Image](https://user-images.githubusercontent.com/103288212/168502785-cd79c997-20c1-4eaa-8038-b6c55f4c8478.png)


## Setup Github Access from ieng6

Where the `ssh` keys are stored on github:

![Image](https://user-images.githubusercontent.com/103288212/168503263-17bfa5cc-6680-4415-88a1-8f9cd8e8d90e.png)

Where the `ssh` keys are stored on the server:
![Image](https://user-images.githubusercontent.com/103288212/168502993-f885a0cf-8efa-4fda-b642-4747697a9b6e.png)

Running `git` commands to commit and push a change to Github while logged into ieng6 account:

![Image](https://user-images.githubusercontent.com/103288212/168672876-d9968e84-5fb1-4903-af21-113e1ffca842.png)
![Image](https://user-images.githubusercontent.com/103288212/168674721-2ce27a39-c02d-4ee3-9d56-d18ad9f77134.png)


[Link to commit](https://github.com/ima-quack/markdown-parser/compare/main...kl2024:main)

## Copy whole directories with `scp -r`

Copying your markdown-parse directory to my ieng6 account:
![Image](https://user-images.githubusercontent.com/103288212/168675650-3db552ea-2b03-4d07-a1ba-a68ced388861.png)

Running markdown-parser (tests should fail because I just changed them to the code to the one from this week's quiz):
![Image](https://user-images.githubusercontent.com/103288212/168675930-3863fa5e-a320-4a15-a845-6cc018c274ad.png)

