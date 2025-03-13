# For GPU providers

If you have:

☑️ Linux-based servers &#x20;

☑️ A computer with a GPU equivalent to RTX 3090 or above ([<mark style="color:blue;">List of eligible GPU models</mark>](../gpu-staking-and-unstaking/staking-requirements.md))

☑️ A public IP address and a worker that can be accessed via SSH

Simply add your GPUs to the network and stake your [<mark style="color:blue;">$tIFX</mark>](https://x.com/search?q=%24tIFX\&src=cashtag_click) tokens to earn passive rewards with the guide below 👇

### Step 1. Log in to the website using a Gmail account

GPU provider website (IoTeX) : [<mark style="color:blue;">https://provider.inferix.io/</mark>](https://provider.inferix.io/)

GPU provider website (Solana): [<mark style="color:blue;">https://miner.inferix.io/</mark>](https://miner.inferix.io/)

⚠️ <mark style="background-color:yellow;">**Note that:**</mark> Once your registration is approved, you will receive an onboarding email shortly from our official email address: <mark style="color:blue;">contact@inferix.io</mark>&#x20;

### Step 2. Set up your account’s wallet address

_The system currently supports the MetaMask wallet plugin._&#x20;

After successful login, go to the Settings page and set the wallet address.&#x20;

⚠️ <mark style="background-color:yellow;">**Note that:**</mark> This wallet address cannot be changed later! All future operations on the website will be linked to this wallet.

### Step 3. Add a GPU Server

3.1. Click **Server** → **Add Servers**, then copy the following comman

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-13 at 22.41.15.png" alt=""><figcaption></figcaption></figure>

3.2. Run the command on your GPU server with root privileges.

⚠️ <mark style="background-color:yellow;">**Note that:**</mark> Currently, only Linux systems are supported.

3.3. Return to the Server page.

* You should see the newly added server with Await Info status.&#x20;
* Click Confirm Info, enter the public IP and port for SSH access, select the GPU model, and submit.
* The server status will change to Pending Review.&#x20;
* You can wait for the operations team to review, or contact them to accelerate the review.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-13 at 22.45.38.png" alt=""><figcaption></figcaption></figure>

3.4. During the Pending Review phase:

* The project team’s operations staff will see the review request in the manage platform.&#x20;
* They will use the SSH IP, port, and key file to log in and verify the machine’s configuration.&#x20;
* If everything is correct, they will approve the machine to join the network.&#x20;
* If your machine remains Pending Review for a long time, you can contact operations for assistance.

### Step 4. GPU Staking

Once the server status changes to Await Stake, you can proceed with staking.&#x20;

Click Stake, and the MetaMask wallet will open, displaying:&#x20;

* The staking amount.&#x20;
* Execution of the smart contract call to lock the staked amount.&#x20;

⚠️ <mark style="background-color:yellow;">**Note that:**</mark> Different GPU models require different staking amounts.&#x20;

After staking, the machine will show as Online, marking its entry into the Testnet for mining.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-13 at 22.48.36.png" alt=""><figcaption></figcaption></figure>
