# Employer Referral User Guide

This guide is meant for employers planning to refer their current or former employees for a loan application at OtRL.

## Required materials
Employers must visit https://bitcoin.org/en/bitcoin-core/ in order to download and install Bitcoin Core on their windows or mac.

## Download and Install Bitcoin Core

1. Visit https://bitcoin.org/en/bitcoin-core/ and select the orange "Download Bitcoin Core" button.

![Bitcoin core landing page](./img/bcc_landing_page.jpg)

2. Select the proper download for your operating system.

![Choose an OS](./img/bcc_download_os.jpg)

3. Double click the executable file in your downloads folder, then select “Yes” in the User Account Control Prompt.

![Run Executable and Allow Permission](./img/bcc_windows_auth.jpg)

4. Select “Next” on the prompt.

![Next](./img/bcc_next1.jpg)

5. Select “Next” on the prompt.

![Next](./img/bcc_next2.jpg)

6. Select “Install” on the prompt.

![Install](./img/bcc_next3.jpg)

7. Select “Next” on the prompt.

![Next](./img/bcc_next4.jpg)

8. Select “Finish” on the prompt.

![Finish](./img/bcc_next5.jpg)


## Start Bitcoin Core

9. Select “Hide” on startup of Bitcoin core if the following screen appears.
    - If the screen does not appear, continue to step 10.

![Hide](./img/bcc_hide.jpg)

10. Select “Create a new wallet”

![Create a new wallet](./img/bcc_create_wallet.jpg)

11. Name the wallet with your desired name and select create.

![Naming and creating the wallet](./img/bcc_wallet_prompt.jpg)

12. Select "Window"

![Select window in the header panel](./img/bcc_select_window.jpg)

13. Select "Console" in the drop down.

![Select console](./img/bcc_select_console.png)

14. Type "getnewaddress 'companyName_public_key' 'legacy'" to produce a public key for your company
    - Note: Your public key may be registered with OtRL, please skip this step if you have an existing public key.

![Get address/public_key from console](./img/bcc_get_address.jpg)

15. Copy the address/public_key provided by the console.

![Copy the address/public_key](./img/bcc_copy_address.jpg)

## Using Bitcoin Core with the Employee Referral Form
This section will require both Bitcoin Core and the Employee Referral Form to be open on your device. Consecutive steps may jump from the Employee Referral Form to the Bitcoin Core application.

16. Navigate to [Referral form](https://main.d2qwhcudgunbox.amplifyapp.com) 

17. Paste the address/public_key into the Employer Identification Field and click "select," your company name should appear on the right hand side and a message should appear below.

18. Copy the message and keep it on hand, it may be helpful to paste it somewhere you can recopy it.

19. Navigate to the Bitcoin core console to sign the message

20. In the console type dumpprivkey followed by your address in quotation marks:
    - EX: dumpprivkey "public_key/address"

21. The output is your private key, copy your private key
  
22. In the console, proceed to type signwithprivkey followed by your private key in quotation marks and the message in quotation marks:
    - EX: signwithprivkey "private_key" "message"
 
23. Your digital signature will be produced, copy the digital signature
 
24. Navigate back to the Referral form and paste the signature in the text box next to digital signature, click "select"

25. Now enter the Employee Unique Identifier for the employee you plan to refer, then click "select"

26. You should now see the employee name and the referral form should have become visible. Follow the instructions on the form and fill out the survey accordingly.

27. Once you have finished the form, click "Submit"
