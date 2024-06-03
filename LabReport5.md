# Part one

## Piazza

**Post Type**

Question

**Post To**

Instructor(s)

**Select Folder(s)**

lab_report5

**Summary**

Looking for help about Some codes

**Details**

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/b7b9694b-10c5-457e-bbf3-02065e2b7e11)

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/f0913c0b-e60f-4a1b-84d3-6cab31526a2a)

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/ef7a132c-75ca-4af7-9659-242bfaf59428)

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/e448d2d0-194a-4e2e-83fe-7fa1c5221862)

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/0698d58d-9346-4630-8e29-126f3ae38d91)

Hi everyone, I have ListExamples.java  and TestListExamples.java here, but the tests run: 2 and failures: 2. So I am looking for help about how to fix the problems.

**Show my name as**

Anonymous to Classmates

---

## the instructors' answer,

Good question!

You are able to see where the bugs are with the test informations. Moreover, you should first ensure your test is correct, and then you can focus on the ListExamples.java.
For example, there is an information "expected:<[a, apple]> but was:<[apple, a]>", so you can try to figure out why the order is reversed.

---

## Fix bugs

For the bug of filter, the test showed the reversed list because in the filter method, the  `result.add(0, s)` this command always add the element at index 0.
So I need to change `result.add(0, s)` to `result.add(s)`, and then it would add element one by one with correct order. When using the vim I just need to move cursor to `0` and then `d2w`. After that 

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/1a9c8759-499b-4934-a4f4-5bb3bb6b5b00)

And then run it again if this would work.

First `:wq` to save and exit.

And then `bash test.sh`.

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/bf4c4984-e970-4416-bc74-b430a13fc742)

It works!

So now I fixed one, and then for the last one.

The messages gives me `test timed out after 100 milliseconds` and `at app//ListExamples.merge(ListExamples.java:42)`

So `vim ListExamples.java` to see the line 42.

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/6530c274-5836-43e7-884b-68717f3af448)

The code `result.add(list2.get(index2))` looks good. But then the next line give me `index1 += 1`. I want to say that it looks good. But this is in a while loop, and the condition `index2 < list2.size()` will not stop since index1 plus one dose not matter with index2. So here I need to change `index1 += 1` to `index2 += 1`.

So here just move cursor to `1` of `index1`, and then use the command `r2` to replace 1 by 2. And then `:wq` to save and exit.

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/681bcb5f-f7be-4fd0-a8c6-183ff0e7d5c6)

Then `bash test.sh` again to see if the change would work.

![image](https://github.com/Klein-Shen/Lab5/assets/165833763/d1e7c83b-715d-4026-a2a4-66eafb3af6ab)

Obviously, it worked.

# Part 2

