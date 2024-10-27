# Summary
Attempted my 2nd CTF exercise today - utilizing the `netcat (nc)` command used in Linux. As per internet definition "it is a networking utility used for *reading from and writing to network connections using TCP or UDP protocols* [^1]".
It is also *network debugging and investigation tool*, capable of producing almost any kind of connection its user could need [^2]. (Yes, sorry na puro internet definition muna tayo).

# Challenge
The challenge is to use `netcat (nc)` to connect with the host `jupiter.challenges.picoctf.org` at port `41120` in order to get the flag.

# Solution
The solution is *straightforward* if you know what you're doing haha (I got stuck lol). We simply have to follow this syntax `nc -host -port`.

![image](https://github.com/user-attachments/assets/3b44507d-5247-493f-8212-54598facfb1e)

*just without the `-` hahaha*

# Final Thoughts
The activity is basically showing the usage of `netcat` as a Linux command, and how it is used to connect to `open` ports of a host server.

[^1]: https://www.geeksforgeeks.org/netcat-basic-usage-and-overview/
[^2]: https://en.wikipedia.org/wiki/Netcat
