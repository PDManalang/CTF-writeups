# Invite Only
## Premise

You are an SOC analyst on the SOC team at Managed Server Provider TrySecureMe. Today, you are supporting an L3 analyst in investigating flagged IPs, hashes, URLs, or domains as part of IR activities. One of the L1 analysts flagged two suspicious findings early in the morning and escalated them. Your task is to analyse these findings further and distil the information into usable threat intelligence.

`Flagged IP: 101[.]99[.]76[.]120`\
`Flagged SHA256 hash: 5d0509f68a9b7c415a726be75a078180e3f02e59866f193b0a99eee8e39c874f`

We recently purchased a new threat intelligence search application called TryDetectThis2.0. (a.k.a `VirusTotal`) You can use this application to gather information on the indicators above.

**Task Link:** (https://tryhackme.com/room/invite-only)

## Questions
### 1. What is the name of the file identified with the flagged SHA256 hash?
In the premise above, SHA256 hash provided `5d0509f68a9b7c415a726be75a078180e3f02e59866f193b0a99eee8e39c874f` let's copy and paste that in `TryDetectThis2.0` search bar.
<img width="1009" height="801" alt="image" src="https://github.com/user-attachments/assets/e0488d26-d7e5-4084-af45-580a5c5985bd" />

Which brings us to the following results:
<img width="953" height="406" alt="image" src="https://github.com/user-attachments/assets/6ade52c6-ce0b-4d8a-ac01-488c2deda941" />

Given the provided results, let's try to find the answer for our first question. We are looking for the `file` identified of the flagged hash - which is `syshelpers.exe` as the `file name`.
<img width="907" height="263" alt="image" src="https://github.com/user-attachments/assets/41ab72c7-25b7-4c4d-ac23-2bc0c62c8a3b" />

### 2. What is the file type associated with the flagged SHA256 hash?
The second question is now looking for the `file type` of the file `syshelpers.exe` which we can locate just below the file name, we have `Win32 EXE`.\
<img width="907" height="263" alt="image" src="https://github.com/user-attachments/assets/08b56c6e-6fbd-4be5-a880-27b615a4834b" />

### 3. What are the execution parents of the flagged hash? List the names chronologically, using a comma as a separator. Note down the hashes for later use.
Next we are ask to look for the `execution parents` of our flagged hash. For us to find it, we go to `Relations` tab where we can find what we are looking for. Thus, the answer for our third question are `361GJX7J` & `installer.exe`. (let's take note also of the hashes below each parent)
<img width="895" height="602" alt="image" src="https://github.com/user-attachments/assets/3a0c5e05-984d-4be3-a5b0-5d8e09391cdc" />

### 4. What is the name of the file being dropped? Note down the hash value for later use.
For our next question, we are looking for a file that was `dropped`, we can also look for this in `Relations` tab - in my case it's just below the `execution parents`. Same thing we did from previous question we are able to get `AClient.exe` as it's file name. (keeping the hash again)
<img width="883" height="415" alt="image" src="https://github.com/user-attachments/assets/552d9031-b593-4bc0-a82e-939660f30ab3" />

### 5. Research the second hash in question 3 and list the four malicious dropped files in the order they appear (from up to down), separated by commas.
Moving on to the `hashes` we got from previous questions, let's observe the hash for `installer.exe` with value `fa102d4e3cfbe85f5189da70a52c1d266925f3efd122091cdc8fe0fc39033942`.
<img width="670" height="298" alt="image" src="https://github.com/user-attachments/assets/3fc14b5d-c739-42e6-8c8a-5527de86f82b" />

Again, we are tasked to list 4 malicious file under `dropped files` (top-down), in this case we have: `searchHost.exe,syshelpers.exe,nat1.vbs,runsys.vbs`\
<img width="432" height="287" alt="image" src="https://github.com/user-attachments/assets/f8327f98-f85c-452c-9f37-392eedc32d11" />\
*Note:* The malicious files are the ones with the `warning` icon on their right most.

### 6. Analyse the files related to the flagged IP. What is the malware family that links these files?
Let us now turn our attention to our `Flagged IP: 101[.]99[.]76[.]120`. We are tasked to look for the malware family that relate to these files. Like always, let's make use of our `TryDetectThis2.0` tool to look for valuable information about the IP.\
<img width="675" height="115" alt="image" src="https://github.com/user-attachments/assets/40daeb0f-f025-4a20-9ae2-ac5b93a88718" />

I initially thought that I'll find answers at `Relations` tab, but instead it's something that we can find under `Community` tab. One of the comments mentiond `IOC Context: AsyncRAT C2`, that must be the malware family that we're looking for.
<img width="872" height="300" alt="image" src="https://github.com/user-attachments/assets/3428e8da-f1ad-4f11-aa02-78b941e24afc" />

### 7. What is the title of the original report where these flagged indicators are mentioned? Use Google to find the report.
Now we're looking for the title report of this flagged indicator (but instead of looking at google), let's observe the community section again (can be really helpful). There's a Title section over here, this must be it? `From Trust to Threat: Hijacked Discord Invites Used for Multi-Stage Malware Delivery`
<img width="872" height="300" alt="image" src="https://github.com/user-attachments/assets/b239287a-9d3e-431b-a616-2511c615df8f" />

### 8. Which tool did the attackers use to steal cookies from the Google Chrome browser?
We are now looking for the tool that the attackers have used to `steal cookies from Google Chrome browser`, this time the `Community` section isn't gonna cut it - let's look at the report directly now.

To make my life a bit easier, I used the browser's ability to find keyword (`CTRL+F`) and searched `cookies` - now we know that the tool they used to for this is `ChromeKatz`.
<img width="1186" height="467" alt="image" src="https://github.com/user-attachments/assets/effb3dc7-9c52-49c6-b06d-33c6d5fd3594" />

### 9. Which phishing technique did the attackers use? Use the report to answer the question.
This time, we are looking for the `phishing technique` they have used. Let's just use the same method we did at item 8. We got `ClickFix`.
<img width="1118" height="290" alt="image" src="https://github.com/user-attachments/assets/ff18bcf2-bc37-418e-b9fd-8197eacb82e7" />

### 10. What is the name of the platform that was used to redirect a user to malicious servers?
Through reading the article, we know that the platform that the attackers used was `Discord`.

**Report Link** (https://research.checkpoint.com/2025/from-trust-to-threat-hijacked-discord-invites-used-for-multi-stage-malware-delivery/)\
*Note:* Might be good to read actually (kahit di ko maintindihan most of it).

> Also, suprisingly this is the first activity na hindi ako masyado umasa sa write-ups ng iba. Definitely beginner friendly.




















