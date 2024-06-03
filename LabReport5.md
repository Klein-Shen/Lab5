# Part one

## Piazza

**Post Type**

Question

**Post To**

Instructor(s)

**Select Folder(s)**

lab_report5

**Summary**

Looking for help

**Details**

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/daafdd16-4b75-435e-b5bd-e45d53690cec)

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/2d6fbda8-b0fc-4c59-9c84-b5b13058b9e4)

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/e00b6529-9eee-4dab-8852-d81b1f6cce81)

Hi everyone, I have a java file and a bash script here, I want to find the some of prime numbers up to the total number I provides. The results I expected for num equals 5 is 2, 3, 5, 7, 11 and 13, but they are 2, 3, 4, 5, 7 and 11.

**Show my name as**

Anonymous to Classmates

---

## the instructors' answer,

Good question!

You can use the jdb command that we have learned in lectures, if you were in there, to check where is wrong.
In your bash script, you may use `javac -g Main.java` to compile the java file so that you can see the local variables.

---

## Fix bugs

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/0d1ea772-b65b-41bc-b97e-67d22cc8d792)

I made changes to the bash script so that I could run the jdb command.

Then `bash run.sh`

`stop at Main:9` since while loop starts at line 9.

`run Main 6`

`next` until the come back to line 9 the third times. At this time, `checkNum` is 4 and I need to check it since 4 should not be in the arraylist.

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/5dd308c2-a630-4ecc-a6a2-a6d6199b1fc1)

For number 4, it should change `isPrime` from 1 to 0, but it did not.

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/3ab5b6a3-79e8-4afe-85bc-38cf3979c2c9)

I could see that, when `checkNum` is 4, it would step over the for loop, so `isPrime` would not be 0.
The reason is because in the condition `int i = 2; i < checkNum / 2; ++i`, from `i = 2` and if `i` less than `checkNum / 2`, which is 2, so it would never step into the for loop.
At first, my idea is to decrease the runtime so I write this condition, but it casued the problem here. An easy way to fix is to remove ` / 2`. And I am gonna try it.

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/412db39b-08ce-4587-a7d7-0e28d8d139b7)

and also I need to make some change for `run.sh` so that I can use `java *` command,

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/ec3ebe38-76e1-4a12-89b9-72ce5ef85deb)

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/74fb6018-6c7e-41f5-8948-063545debd8b)

Obviously, it works.

# Part 2

After a period of study, I have acquired a significant amount of knowledge, including how to use `jdb` to debug on the terminal and how to navigate `vim`. 

Additionally, I have mastered specific commands like the `find` command and the `grep` command I discussed in my previous lab report, both of which boast powerful capabilities. 

These functions not only simplify complex tasks but also streamline intricate operations. Particularly in specialized environments akin to skill demo 4, this knowledge enables me to carry out standard operations, such as locating specific file paths and using `wc` to count lines in files. 

While I have forgotten some details, in the `vimtutor` it emphasizes learning through practical application rather than mere rote memorization. And this can also be applied to the learning of other knowledge.
