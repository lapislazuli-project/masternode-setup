# Masternode Installation Script on Linux Server running Ubuntu 18.04

# Part 1 - Sending Collateral Coins

1. Open your Windows wallet and unlock if your wallet is encrypted - MAKE SURE IT IS FULLY SYNCED WITH THE NETWORK AND STAKING IS DISABLED
2. Go to Settings -> Debug -> Console
3. Type: getnewaddress MN# (# is your masternode number you want to use. Example: MN1)
4. Send 100000 LiLLi to this address and wait for at least 1 confirmation
5. Go to Settings -> Debug -> Console
6. Type: getmasternodeoutputs
7. Type: createmasternodekey
7. Save your TX ID (The first number) and your Index Number (Second number, either a 1 or 0)
8. Save your generated key as well as this will be needed in your VPS as your private key
9. Save these with a notepad
10. Close the wallet
11. Move to Part 2 if you use a VPS with root login. If you use a Masternode Hosting service then continue with the tutorial provided by the Masternode Hosting service.

# Part 2 - Getting your Linux VPS Started Up (Read all instructions and follow prompts closely)

1. Connect to your linux vps AS ROOT, copy and paste the following line into your VPS. Double click to highlight the entire line, copy it, and right click into Putty or Shift + Insert to paste or other button combinations depends on the shell application or your system operation.
```
bash <( curl -sL https://raw.githubusercontent.com/lapislazuli-project/masternode-setup/main/masternodeinstall.sh)
```
2. follow the prompts closely and don't mess it up!
3. Move to Part 3

# Part 3 - Editing your Windows Config File

1. Open masternode.conf file
2. Enter the following on one single line after the example configuration
```<alias> <ip>:19330 <private_key> <tx_id> <index>```
3. It should look something like this:
``` MN1 127.0.0.2:19330 XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX X```
4. Save and close the file and restart your wallet.

# Part 4 - Starting the Masternode

1. In your wallet, go to Masternode tab
2. Click on the masternode you just created and click start
3. Enjoy! You can start this process over again for another MN on a fresh installed Linux VPS!

# Part 5 - Checking Masternode Status

1. After running the command in step 4, go back to your VPS
2. Enter ```cd /usr/local/bin/lapislazuli-v1.0.0-x86_64-linux```
3. Enter ```./lapislazuli-cli getmasternodestatus```
4. This will tell you the status of your masternode, any questions, Join discord for help: https://discord.gg/xHGpGC8RVy

# Recommended Tools

- Windows Powershell can be used as SSH client.
- Putty - Easy to use and customizable SSH client.