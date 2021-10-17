# Methodology - Special

:loop: **Github access token exposure**

I was reviewing an Electron app made by one of Shopify employees (at the time I didn't know that Shopify was in any way involved), after extracting the <kbd>app.asar</kbd> file using <kbd>npx asar extract path/to/app.asar extracted/path</kbd> I found a <kbd>.env</kbd>file, initially I skipped it because I thought it just contained some app configuration stuff but after taking a look at the source it was clear that the app never loaded it. It was probably a leftover of the release building process.

That <kbd>.env</kbd> contained a <kbd>GH_TOKEN</kbd> variable, which is (as you can probably guess) a GitHub token, I tried using it to authenticate against GitHub REST API using <kbd>curl -H "Authorization: token $GH_TOKEN" -H "Accept: application/vnd.github.v3+json" https://api.github.com/user</kbd> I saw that the token was indeed valid so I decided to hit the <kbd>/user/orgs</kbd> API endpoint and I got back (among others) the Shopify organization, then I hit the <kbd>/orgs/Shopify/repos</kbd> endpoint to confirm the GitHub token scope and I successfully got back a list containing both Shopify public and private repos with <kbd>"permissions": {"admin": false, "push": true, "pull": true}</kbd> so at that point I knew that the token was enabling me to perform arbitrary push and pulls to Shopify repos so potentially permitting me to place backdoors and such.

While dissecting an application made by one of your employees I found his GitHub Personal Access Token (PAT), he's a member of the org with pull and push access to all of your repositories.
As a proof I can tell you that on the repo github.com/Shopify/shopify at commit hash <kbd>cea9c273391d</kbd> the sha512 of the README.md is <kbd>69750574bec56c1f1052db3471252b1daacdc9dda9f6d5332a3400a847fa413ec1caf19ef0b5501f18a5a76c232e7210d5f3b91c24c9439f4e0f64c02d6db824</kbd>.

**Impact**</br>
Read and write access to all your private github repositories.

Hi,
the application I was reviewing is ██████, made by ████████ ███████.
After extracting the <kbd>app.asar</kbd> file (download the macOS version, extract from the dmg the file at path <kbd>█████.app/Contents/Resources/app.asar)</kbd>, you extract the asar archive contents <kbd>asar extract app.asar asar-out-dir</kbd> and you see that in the output directory there'll be a <kbd>.env</kbd> file containing some credentials, one of those is one of █████'s PAT issued with global scope, so a malicious actor can access every repo under Shopify GitHub org with r/w access using that.

Hi @augustozanellato,
Thanks again for the report. We’ve revoked this GitHub Personal Access Token. To aid in our investigation, we would appreciate if you could provide the IP address(es) from which you performed your testing and a list of actions you performed on the Shopify organization using the token.
You should hear back from us within 7 days regarding a bounty decision.

Hi,
the IP used for the tests is ██████████, the actions performed on the Shopify org were limited to GET <kbd>/orgs/Shopify/repos</kbd> in order to list the repos and I tried to actually start some clones because I couldn't believe it was real :P. I also cloned in <kbd>/tmp</kbd> the shopify repo in order to give you the hash of README.md. Maybe I shouldn't have done that, but I had no idea how to approach this. Rest assured that all the data was properly destroyed after providing you with the hash.

**Reference:**
</br>[https://hackerone.com/reports/1087489](https://hackerone.com/reports/1087489)
