# Adding GPUs to the Network

1. **Log in to the Website**\
   Use your Gmail account to log in at: [https://provider.inferix.io/](https://provider.inferix.io/)
2. **Set Up the Wallet Address** \
   The system currently supports the MetaMask wallet extension. After successfully logging in, navigate to the _**Settings**_ page and configure your wallet address. Please note that this address cannot be changed later, and all subsequent website operations will be linked to this wallet.
3. **Add GPU Servers** \
   A. Go to _**Server → Add Servers**_, and copy the command line provided\
   \
   ![](<../.gitbook/assets/image (13).png>)\
   \
   B. Run the command on your GPU server with root privileges. Currently, only Linux-based servers are supported for joining the network. \
   \
   C. Return to the _**Server**_ page, and you will see the server you just added displayed with the status _**Await**_ Info. Click the _**Confirm Info**_ button, fill in the public IP and port for SSH access, select the GPU model, and submit. The server's status will change to _**Pending Review**_. At this point, you can either wait for our operations team to review it or actively contact us to expedite the review process.\
   \
   ![](<../.gitbook/assets/image (14).png>)\
   \
   D. While the server is in the _**Pending Review**_ status, the operations team will see the review request on the management platform. They will use the provided SSH IP, port, and key file to log in to the server and verify its configuration. If everything checks out, they will click _**Approve**_ to allow the server to join the network. If the server remains in the _**Pending Review**_ status for an extended period, you can contact the operations team for assistance\

4. **GPU Staking** \
   When the provider user sees the server status change to _**Await Stake**_ on their _**Server**_ page, they can proceed with the staking operation. Clicking the **Stake** button will trigger the MetaMask wallet, displaying the staking amount. This action will call the smart contract to lock the staking amount within it. \
   \
   It’s important to note that the staking requirements vary based on the GPU model. Please refer to the table below for details.\
   \
   ![](<../.gitbook/assets/image (16).png>)\
   \
   Once the staking operation in the previous step is completed, the server status will change to _**Online**_, indicating that it has successfully joined the Inferix\_Testnet and started mining
