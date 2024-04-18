Demonstrate a session replay attack on the Pizza House website that uses session management policies. Also employ appropriate countermeasures against such an attack.

 Procedure for implementation:
Demonstration of Session Replay Attack:

1. Scenario Setup: The attacker intercepts network traffic between a legitimate user and the Pizza House website during a login session.

2. Capture Session Cookie: Using tools like Wireshark, the attacker captures the session cookie transmitted during the legitimate user's login process.

3. Replay Attack: The attacker replays the captured session cookie in their own browser or through automated tools, such as cURL, mimicking the legitimate user's session.

4. Unauthorized Access: With the replayed session cookie, the attacker gains unauthorized access to the Pizza House website, effectively impersonating the legitimate user. They can perform actions like placing orders, viewing account details, or accessing sensitive information.

Appropriate Countermeasures:

1. HTTPS Implementation: Pizza House should enforce HTTPS for their entire website to encrypt communication between the user's browser and the server, making it difficult for attackers to intercept and capture session cookies.

2. Session Token Expiration: Implement session token expiration policies to invalidate session tokens after a certain period of inactivity, reducing the window of opportunity for attackers to replay captured tokens.

3. IP Address Verification: Pizza House can implement IP address verification mechanisms to ensure that the IP address associated with the session matches the IP address from which the original login occurred, detecting potential session replay attacks.

4. User-Agent Verification: Validate the User-Agent header of incoming requests to ensure they match the characteristics of the user's browser, preventing automated replay attacks.

5. Anti-CSRF Tokens: Implement anti-CSRF tokens to prevent attackers from forging requests using stolen session cookies, adding an extra layer of security to sensitive actions.

6. Session Regeneration: Regenerate session identifiers after significant actions such as login, logout, or account setting changes to invalidate previously captured session cookies.


Results and inference from the project:
We logged in using session id and prevented it using strong session management and safekeeping policies.



Cookies in browser: 
![image](https://github.com/lobhasap/Session-Replay/assets/142318426/c7888b23-7e68-4ba1-a3a6-27a3416b8a73)

 


Logged cookies in file (server side):  
![image](https://github.com/lobhasap/Session-Replay/assets/142318426/addd8439-fce5-4de7-ab1c-879968a5bed2)




Command for session replay attack:
Invoke-WebRequest -Uri "http://localhost:3000/index.html?username=admin" -Method GET -Headers @{"Cookie"="4a5d2eexo"; "X-Client"="Terminal"; "User-Agent"="PowerShell"}



Output:
![image](https://github.com/lobhasap/Session-Replay/assets/142318426/5d242570-3734-4539-a712-4338c05ad26f)
 
