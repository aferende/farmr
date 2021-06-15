# farmr

A web dashboard that allows you to monitor your Chia farm and sends notifications when blocks are found and new plots are completed through a discord bot. It can link multiple farmers/harvesters to your account.

![image](https://user-images.githubusercontent.com/82336674/121625370-41d93f00-ca6b-11eb-9152-03cabc89a1b6.png)

The farmr client collects local stats about your farm and it is available for Windows, Linux and macOS [here](https://github.com/joaquimguimaraes/chiabot/releases/latest). 
The dashboard can be found in [farmr.net](https://farmr.net). Alternatively, you can interact with the bot in [Swar's Chia Community](https://discord.gg/q5T4QbwcnH) discord server. You must be in this server to receive notifications.

### farmrBot commands
| ``!chia`` command | Block, Plot and Offline notifications |
|-----------------------------------------------------|-------------------|
|![screenshot](https://i.imgur.com/ilPYPe3_d.webp?maxwidth=450&fidelity=grand)|![notifications](https://i.imgur.com/HXKroKS_d.webp?maxwidth=450&fidelity=grand)|

| ``!chia full`` for detailed stats | ``!chia workers`` for client-specific stats |
|------------------------|-------------------|
|![chiafull](https://i.imgur.com/7GEM6Z3_d.webp?maxwidth=450&fidelity=grand)|![chiaworkers](https://i.imgur.com/2AOeYcR_d.webp?maxwidth=450&fidelity=grand)|

| Challenge Parsing | Full Node stats |
|------------------------|-------------------|
|![challenges](https://i.imgur.com/PpmlJj6_d.webp?maxwidth=450&fidelity=grand)|![fullnode](https://i.imgur.com/R1OOemY_d.webp?maxwidth=450&fidelity=grand)|

## Installation 
Proceed with the following platform-specific instructions:

#### Windows
1. Download ``farmr-windows-amd64.zip`` from the [latest release](https://github.com/joaquimguimaraes/chiabot/releases/latest) and extract it to an **empty** folder.

- If you're setting up a **farmer/full-node** (need to have at least 1 farmer/full-node linked to your account)
   1. Open ``farmer.exe``, once you see the main screen with your id and farmer stats you're good to go.
   2. Link your device to your discord account as shown in [First Time](#first-time)

- If you're setting up a **harvester**
   1. Open ``harvester.exe``, once you see the main screen with your id and harvester stats you're good to go.
   2. Link your device to your discord account as shown in [First Time](#first-time)

Do not run both ``farmer.exe`` and ``harvester.exe`` in the same PC at the same time!


#### Ubuntu (16.04+), and other amd64 Linux distros
1. Download ``farmr-linux-amd64.tar.gz`` from the [latest release](https://github.com/joaquimguimaraes/chiabot/releases/latest) and extract it to an **empty** folder.
2. Open the following file:
      - If you're setting up a **farmer/full-node** Open ``farmer.sh``, once you see the main screen with your id and farmer stats you're good to go.
      - If you're setting up a **harvester** Open ``harvester.sh``, once you see the main screen with your id and harvester stats you're good to go.
3. Link your device to your discord account as shown in [First Time](#first-time)

If you're on ubuntu and can't open ``farmer.sh`` or ``harvester.sh`` from file explorer you can run this command:
```
gsettings set org.gnome.nautilus.preferences executable-text-activation ask
```
Then reopen file explorer in the folder where ``farmr-linux-amd64.tar.gz`` was extracted to. You should be able to double click ``farmer.sh`` or ``harvester.sh`` and let it "Run in terminal" when asked to.


#### Ubuntu for Raspberry Pi and other arm64 Linux distros
1. Download ``farmr-linux-arm64.tar.gz`` from the [latest release](https://github.com/joaquimguimaraes/chiabot/releases/latest) and extract it to an **empty** folder.
2. Open the following file:
      - If you're setting up a **farmer/full-node** Open ``farmer.sh``, once you see the main screen with your id and farmer stats you're good to go.
      - If you're setting up a **harvester** Open ``harvester.sh``, once you see the main screen with your id and harvester stats you're good to go.
3. Link your device to your discord account as shown in [First Time](#first-time)


#### macOS (use Rosetta for m1 devices)
1. Download ``farmr-macos-amd64.tar.gz`` from the [latest release](https://github.com/joaquimguimaraes/chiabot/releases/latest) and extract it to an **empty** folder.
2. Open the following file:
      - If you're setting up a **farmer/full-node** Open ``farmer.sh``, once you see the main screen with your id and farmer stats you're good to go.
      - If you're setting up a **harvester** Open ``harvester.sh``, once you see the main screen with your id and harvester stats you're good to go.
3. Link your device to your discord account as shown in [First Time](#first-time)

#### HPool Mode
You can use farmr for basic stats if you are farming in HPool. Follow the instructions above according to your platform. Just make sure you run ``hpool.exe`` or ``hpool.sh`` and then set ``"HPool Directory"`` and ``"HPool Auth Token"`` in ``config.json``. Then reopen ``hpool.exe`` or ``hpool.sh``.
farmr client uses this auth token locally and it is never sent to farmr's servers.

#### FoxyPool (chia-og) Mode
farmr can show your pending and collateral balances from FoxyPool. Follow the instructions above according to your platform. Just make sure you run ``foxypoolog.exe`` or ``foxypoolog.sh`` and then set ``"Pool Public Key"`` in ``config.json``. Then reopen ``foxypoolog.exe`` or ``foxypoolog.sh``.
farmr client uses this key locally and it is never sent to farmr's servers.


#### Compile from source (every platform/architecture)
1. Download ``source.tar.gz`` or ``source.zip`` from the [latest release](https://github.com/joaquimguimaraes/chiabot/releases/latest) and extract it to a folder.
2. Download and install [dart sdk](https://dart.dev/get-dart)
3. Open the terminal in the folder you just extracted and run:
   - If you're setting up a **farmer**:
```
dart pub get; 
dart run environment_config:generate;
dart compile exe farmr.dart; 
mv farmr.exe farmr;
```
   - If you're setting up a **harvester**:
```
dart pub get; 
dart run environment_config:generate;
dart compile exe farmr_harvester.dart; 
mv farmr_harvester.exe farmr;
```
4. Run ``./farmr`` once you see the main screen with your id and farmer/harvester stats you're good to go.
5. Link your device to your discord account as shown in [First Time](#first-time)

### First time
The farmr client will generate an id for your device. 
After you've logged in to [farmr.net](https://farmr.net), you can link this device by clicking on "Add device" in the upper right corner of the dashboard, where you can copy and paste the random id (e.g.: ``e134104c-0e2e-49e0-a832-985c5a5e4516``) and then click "Add".

![tutorial](https://user-images.githubusercontent.com/82336674/121625132-c4adca00-ca6a-11eb-8906-c3d90bbf85c0.gif)

Alternatively, you can link this device to your discord account by heading to [Swar's Chia Community](https://discord.gg/q5T4QbwcnH) and sending the following message:
```
!chia link [your-client-id]
```
The client will save your id in its cache file (``.farmr_cache.json``), so you only need to run this command once per device. Mind you that you will need to do this again if this file gets deleted/corrupt.

## Usage
If your device was linked sucessfully, you will see two new tiles appear from the left (may need to refresh page). One called ``Farm`` and the other with the name of your newly added device.
``Farm`` tile is the overall statistics for your farm (multiple devices), while the other tiles will show individual statistics for each device that is linked to your account.

 Alternatively, you can use `` !chia `` in discord to see your farm summary, or `` !chia full `` to display additional statistics about it and `` !chia workers `` to show them per farmer/harvester.
To see the full list of commands you can use, type: `` !chia help ``

You **must not close the clients' console window** as doing that will kill the client and it will stop sending statistics. If you do so, open it again.
Press ``ctrl+c`` when you want to close the client. You must reopen it after restarting your computer.

### Configuration
farmr client stores your current configuration in ``config.json``
You do not need to edit this file, as it's automatically generated by farmr. However, you may wish to customize some of its options.
If you wish to do so, you can rename ``config.json.default`` to ``config.json`` to change them.
These are the default settings:
```json
[
    {
        "Name": "Harvester",
        "Currency": "USD",
        "Show Farmed XCH": true,
        "Show Wallet Balance": false,
        "Block Notifications": true,
        "Plot Notifications": false,
        "Hard Drive Notifications": true,
        "Offline Notifications": false,
        "Farm Status Notifications": true,
        "Parse Logs": false,
        "Number of Discord Users": 1,
        "Public API": false,
        "Swar's Chia Plot Manager Path": ""
    }
]
```

#### Name your client
You can name your client by changing `` "Name": "Harvester",`` to ``"name": "YourFarmer",`` (notice **quote marks**). This will identify the client as ``YourFarmer`` in `` !chia workers ``.

#### Choose your preferred currency
Replace ``"USD"`` with any of the following 3-digit symbols: ‘USD’, 'EUR', 'CAD', 'GBP', 'AUD', 'SGD', 'JPY', 'INR', 'RMB', 'CNY', 'CHF', 'HKD', 'BRL', 'DKK', 'NZD', 'TRY', 'ETH', 'BTC', 'ETC'.

#### Sharing farmed XCH Balance
Set ``Show Farmed XCH`` to ``false`` if you do not want your farmed balance to be reported to the server. Setting this to false will disable Block notifications.

#### Sharing Wallet Balance
Set ``Show Wallet Balance`` to ``true`` if you want your wallet balance to be displayed.

#### Block Notifications
Set ``Block Notifications`` to ``false`` if you do not wish to be notified when your farmer finds a block.

#### Plot Notifications
Set ``Plot Notifications`` to ``true`` if you wish to be notified when your farmer/harvester completes a plot.

#### Hard Drive Notifications
Set ``Hard Drive Notifications`` to ``false`` if you don't want to be notified when your farmer/harvester loses connection to one of its drives.

#### Offline Notifications
Set ``Offline Notifications`` to ``true`` if you wish to be notified when your farmer/harvester loses connection.

#### Status Notifications
Set ``Farm Status Notifications`` to ``false`` if you don't want to be notified when your farmer loses sync and stops farming. If you have log parsing enabled, you will also be notified if your harvester stopped receiving challenges.

#### Chia Log Parsing
If your chia debug level is set to ``INFO`` ([find how to do that here](https://thechiafarmer.com/2021/04/20/how-to-enable-chia-logs-on-windows/)), setting ``Parse Logs`` to ``true`` will enable extra stats, such as number of challenges in the last 24 hours, max, min and average challenge response times, incomplete SubSlots, and number of short losses of sync events.

#### Multiple Discord Users
Change ``Number of Discord Users`` if you would like to link your farmer/harvester to more than one discord user. It will generate one unique ID per user.
You may delete ``config.json`` and ``.farmr_cache.json`` to reset settings and generate new ids once the client is started again.

#### Public API
Set ``Public API`` to true if you want your data to be accessed from farmr's api page (``!chia api`` will show you your link)

#### Swar's Chia Plot Manager Integration (experimental)
If you are running Swar's Plot Manager >v0.1.0 then you can set ``"Swar's Chia Plot Manager Path"`` to the path where it's installed.
Notice that if you run it in a python venv then you must launch the farmr client in this venv. Current jobs will be displayed at the bottom of ``!chia full`` and ``!chia workers``

#### HPool Mode
Set ``HPool Directory`` to the path that leads to the directory containing hpool's ``config.yaml``.
You need to set ``HPool Auth Token`` to the ``auth_key`` string in your hpool.com cookies. To see this token, open your browser and login to hpool.com, then right-click anywhere on the page and click on ``Inspect Element``, you should see a panel appear with a "Storage" tab. Right click on the string next to "auth_key" and copy that string string in ``value`` column. That's the string you should use as ``HPool Auth Token`` in farmr's ``config.json``. You should only need to update this value once every 3 months or when you logout from that device.
![image](https://user-images.githubusercontent.com/82336674/120874560-063c0200-c59f-11eb-8110-2be81469651b.png)

### Upgrading
To upgrade, repeat [Installation](#installation) instructions again with the [latest release](https://github.com/joaquimguimaraes/chiabot/releases/latest).
If you wish to keep its settings, move ``config.json`` from the previous installation folder to the new folder.
Similarly, you may keep the previous cache file by doing the same with ``.farmr_cache.json``. This file is hidden in Linux/macOS.

### Troubleshooting

##### My farmer/harvester doesn't have plots. Can I still use farmr?
Yes, your client will add itself when chia completes a plot.

If the client crashes:
##### Is your chia farm running? 
  You can check this by running ` chia farm summary `, if it shows "Status: Farming", then it is.
##### Are your plot drives mounted?
  If they're not, then mount them.
##### Does your user have permission to access the folders where plots are stored?
  farmr will not be able to list your plots if their folder was mounted as root.

##### What if I have two or more farmers?
  Run one of them as a farmer and the others as harvesters.
 
##### Help, I linked the same device twice and it's showing two devices.
  Inactive clients will expire after 15 minutes.
  
## FAQ

##### Are you going to steal my keys?
No. The only commands issued by farmr client is ``chia farm summary`` for farmer stats, ``chia wallet show`` for wallet balance parsing and ``chia show -c`` to count how many peers are connected to your full node. It does not use Chia's RCP servers, therefore it doesn't even need your private key.

##### How can I trust you?
This project is open-source, so you don't have to trust me. Read the code yourself :)
Besides, every binary is built by a github action and signed with a GPG key.

##### What data is collected?
You can see the data that's currently tied to your discord ID with ``!chia api``
Your wallet address is not sent to the server so your data remains anonymous (that is, except being linked to your discord ID).

##### What if I don't want my data to be stored in your server anymore?
Simple, stop using it. All data will be deleted 15 minutes after your client sent its last report.

## Donate
@joaquimguimaraes wallet addresses:
```
XCH: xch1z9wes90p356aqn9svvmr7du8yrr03payla02nkfpmfrtpeh23s4qmhx9q9
ETH: 0x340281CbAd30702aF6dCA467e4f2524916bb9D61
LTC: LWPkaD4P7bKpU28RTV4sP41jnrQ3NMDs5y
ADA: addr1q8uw5jh3q0eujj6gqngrdgvr7r6gvqj5qv6tsp77d6usgcv6jehyxjelvffwv53r0avad874vk6snsq3tmmj7z27w73s9kxdkv
USDC (ERC20/BEP20): 0x340281cbad30702af6dca467e4f2524916bb9d61
USDT (ERC20/BEP20): 0x340281cbad30702af6dca467e4f2524916bb9d61
USDT (TRC20): TFddaDuxHUFvtuhLtwodQmNB4ZjJRc4P8k
BNB: 0x340281cbad30702af6dca467e4f2524916bb9d61
BTC: 1Gdzsx6VjZrDxP43y1pgkNMZGsyL357odS
BTC (BEP20): 0x340281cbad30702af6dca467e4f2524916bb9d61
```


## Acknowledgements
Dashboard's structure based on the work by Abu Anwar MD Abdullah [@abuanwar072/Flutter-Responsive-Admin-Panel-or-Dashboard](https://github.com/abuanwar072/Flutter-Responsive-Admin-Panel-or-Dashboard), licensed under MIT license.

[Poppins font](https://fonts.google.com/specimen/Poppins#standard-styles) designed by Indian Type Foundry, Jonny Pinhorn, licensed under Open Font License.

Icons by Google and [Material Design Icons](https://materialdesignicons.com/)


This project is not affiliated with [Chia Network™](https://www.chia.net/).
