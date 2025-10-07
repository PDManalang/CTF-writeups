
Who is the individual who received an email attachment containing a PDF?
This one is straightforward, we review all the phishing email reports and look through the file attachments within each email.
<img width="949" height="61" alt="phishing-pdf" src="https://github.com/user-attachments/assets/f9a36d85-a3ee-419d-894e-d9af15a49b9d" />

What email address was used by the adversary to send the phishing emails?
Looking at the sender of the email.
<img width="708" height="29" alt="image" src="https://github.com/user-attachments/assets/e3b81009-e225-4efa-8844-560034a9ef94" />

What is the redirection URL to the phishing page for the individual Zoe Duncan? (defanged format)
In order for us to not able to directly access the link, we'll open url details via notepad (or any text editor).
<img width="500" height="363" alt="image" src="https://github.com/user-attachments/assets/35f0ff90-9a6c-4031-94e1-060b542927b3" />

And as the answer seeks a `defanged format` we'll be using CyberChef to aid us on this.
<img width="1530" height="853" alt="image" src="https://github.com/user-attachments/assets/fd51d6ab-5c83-4d64-b622-6c52fc71e1ff" />

What is the URL to the .zip archive of the phishing kit? (defanged format)
In order to get access to this `.zip`, we'll visit the earlier url we got `http://kennaroads.buzz/data/`, which will show us this:
<img width="949" height="818" alt="image" src="https://github.com/user-attachments/assets/21c39400-f319-4484-984a-9c50977f646a" />
Let's then get the url for `Update365.zip`:
<img width="495" height="493" alt="image" src="https://github.com/user-attachments/assets/884d2333-5e9c-4f03-a593-bc523b5e9030" />
Then let's use CyberChef again to 'defanged the format':
<img width="1528" height="846" alt="image" src="https://github.com/user-attachments/assets/3821721d-0d46-40ad-9468-9bba3f0a4d27" />

What is the SHA256 hash of the phishing kit archive?
download the phishing kit `.zip` then input the following on the terminal: `sha256sum Update365.zip`
<img width="732" height="65" alt="image" src="https://github.com/user-attachments/assets/31e9812c-a08d-46fd-aded-d028ef9075b5" />

When was the phishing kit archive first submitted? (format: YYYY-MM-DD HH:MM:SS UTC)
Now that we got the hash of this phishing kit, let's find out when it was discovered and submitted (to report) thru `VirusTotal`
<img width="1911" height="162" alt="image" src="https://github.com/user-attachments/assets/96dfa4d5-3faa-491d-86e9-39a368ee0a59" />

When was the SSL certificate the phishing domain used to host the phishing kit archive first logged? (format: YYYY-MM-DD)
We used ThreatBook Intelligence for this exercise
<img width="1915" height="970" alt="image" src="https://github.com/user-attachments/assets/8eb6ada1-6d32-4523-90c5-3bb94b0d2040" />

What was the email address of the user who submitted their password twice?
Going back to `http://kennaroads.buzz/data/Update365/` let's explore the `log.txt` where the login history is recorded
<img width="952" height="822" alt="image" src="https://github.com/user-attachments/assets/c3f374a4-9f0b-4654-8e4a-2d4288f15931" />

What was the email address used by the adversary to collect compromised credentials?
Let's explore the zipped file, and lookthrough one of the scripts:
<img width="949" height="821" alt="image" src="https://github.com/user-attachments/assets/23ef89f2-56ac-40c5-9eac-7bc5d073f63b" />

The adversary used other email addresses in the obtained phishing kit. What is the email address that ends in "@gmail.com"?
Take the time to read through the scripts...
<img width="954" height="821" alt="image" src="https://github.com/user-attachments/assets/a902f6ce-c1e1-4494-877c-b6fe27a866ef" />

What is the hidden flag?
To find the hidden flag...
<img width="729" height="102" alt="image" src="https://github.com/user-attachments/assets/d071e374-93d8-47d7-941e-f0455ff7cf15" />
oop.. not quite. let's try to decode this
<img width="742" height="70" alt="image" src="https://github.com/user-attachments/assets/8bb94f93-3ab4-4b4e-87b2-834030a5e9d2" />
Hmm. This still doesn't look convincing...
<img width="953" height="76" alt="image" src="https://github.com/user-attachments/assets/76859f55-92bc-4b3f-9a91-495f83624bf5" />
Here we go
<img width="732" height="63" alt="image" src="https://github.com/user-attachments/assets/a71279be-571e-40b4-828e-96712f9cc9b1" />

Hirap ayaw ko na. HAHAHAHA emz.
(reference later)



















