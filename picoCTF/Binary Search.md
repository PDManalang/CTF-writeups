# Summary
Today is the first day I did my CTF using picoGYM - a place where I can practice doing CTFs before joining actual events. Before this, I joined the practice CTF of HTB - but as I get along the tasks, I just couldn't get my head around it (yet). Luckily, I get to learn about picoCTF and it's beginner friendly activities - so I gave it a shot. And *Binary Search* is the CTF activity I get to finish.

# Challenge
The challenge is basically guessing the correct number within 1-1000 options you have, where the difficult part is that if you only have 10 chances to get the correct answer.

# Solution
The game is all about maximizing the *Binary Search* algo - which is a classic algorithm that is used to quickly find an item in a sorted list.

1) As starting point, we will be using this formula `mid = (low + high) / 2` to get the middle number - this will help us minimize our options in half.

![image](https://github.com/user-attachments/assets/235fdf94-9c8b-4834-9245-eaf1bfd893fa)

this already gave us an idea if we should guess or number in a lower or higher range of options. In this case, we know that our number flag is below 500.

2) We will continue to use the `mid = (low + high) / 2` formula, until our options gets smaller.

![image](https://github.com/user-attachments/assets/ce82b5a4-5d61-46e7-9bb7-8a21e2dab542)



