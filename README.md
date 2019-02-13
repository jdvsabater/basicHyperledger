================================

Environment: 

Host: Windows 10 Pro (64-bit) version 1809 / Core m-5y51 / 8GB RAM / 256GB SSD

Virtualization software: VMware Workstation Pro 15 (VirtualBox 5.2.22 will do)

Guest: Ubuntu 16.04.5 LTS (64-bit), Config: 4GB RAM / 40GB Storage

================================
Setting up the files:


- Clone this repository.

- Replace the files from hyperledger/fabric-samples from this repository

- Go to fabric-samples/fabcar inside the terminal

- First, enter ./openScm.sh 

- Enter: node enrollAdmin.js

- (Optional) Enter: node registerUser.js

- (Optional) Enter: node rSupplier1.js

- (Optional) Enter: node rOEM.js

- To test the functions, enter : node app_scm.sh

- To test the functions as a supplier1, enter : node appSupplier1.sh

- To test the functions as a OEM, enter : node appOEM.sh
    
- Open Postman

- To display the invoice, set the method to GET, then type localhost:<Port>/queryAllinvoice in the address bar and click Send.

- To enter an invoice, set the method to POST, then go to the body tab, and click x-www-form-urlencoded

   Type in the following keys: (one key per line, case-sensitive)

         Key            Value (sample)
    
    invoiceNumber       INV002
    billedTo            Lenovo
    invoiceDate         2/9/2019
    invoiceAmount       50000
    itemDescription     any description here
    gr                  no
    isPaid              no
    paidAmount          0
    repaid              no
    repaymentAmount     0

   Type localhost:<Port>/invoice in the address bar and click Send.

- Then set the method to GET, then typelocalhost:<Port>/queryAllinvoice in the address bar and click Send. To see the invoice that you had entered.

- To set the goods to received in an invoice, set the method to PUT, go to Body tab, and tick x-www-form-urlencoded

   Type in the following keys: (one key per line, case-sensitive)

         Key            Value (sample)
    
    invoiceNumber       INV002
    gr          yes

- Then set the method to GET, then typelocalhost:<Port>/queryAllinvoice in the address bar and click Send. To see the invoice that you had entered.

- To pay the supplier by bank, set the method to PUT, go to Body tab, and tick x-www-form-urlencoded

   Type in the following keys: (one key per line, case-sensitive)

         Key            Value (sample)
    
    invoiceNumber       INVxxx
    isPaid          yes
    paidAmount      49000 (this must be less than the invoiceAmount)

- Then set the method to GET, then typelocalhost:<Port>/queryAllinvoice in the address bar and click Send. To see the invoice that you had entered.

 To repay the bank by OEM, set the method to PUT, go to Body tab, and tick x-www-form-urlencoded

   Type in the following keys: (one key per line, case-sensitive)

         Key            Value (sample)
    
    invoiceNumber       INVxxx
    repaid          yes
    repaymentAmount     51000 (this must be greater than the paidAmount)

   Type localhost:<Port>/invoice in the address bar and click Send.

- Then set the method to GET, then typelocalhost:<Port>/queryAllinvoice in the address bar and click Send. To see the invoice that you had entered."# basicHyperledger" 
"# basicHyperledger" 
"# basicHyperledger" 
