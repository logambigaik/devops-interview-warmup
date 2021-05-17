# U have cloned the git repo and renamed it in your local dircetory. How do you get the actual git repo location (original git repo)?

``` git remote -V ```

![image](https://user-images.githubusercontent.com/54719289/118531317-9d026500-b73d-11eb-8428-6faee9b9003c.png)


# 
![image](https://user-images.githubusercontent.com/54719289/118531460-c4f1c880-b73d-11eb-9f6f-18e73321dbb0.png)

``` Answer is git clone -b branchname --depth 1 git-url ```

![image](https://user-images.githubusercontent.com/54719289/118532194-958f8b80-b73e-11eb-87f8-84f597c1e912.png)


# What is submodule? Why do we need to use?

![image](https://user-images.githubusercontent.com/54719289/118532478-eb643380-b73e-11eb-84e8-dc0db492d78a.png)
![image](https://user-images.githubusercontent.com/54719289/118532546-fb7c1300-b73e-11eb-8c82-2c4c11b96324.png)

## There is a disadvantage in submodule. Submodules dont track refs or branch and are not automatically updated when host repo is updated
