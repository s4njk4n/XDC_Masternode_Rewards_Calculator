# XDC Masternode Epoch Rewards Calculator

See how much an XDC masternode owner address earned in epoch rewards over any period: for tax time, reporting, or just checking your node is paying out.

**[Open the calculator →](https://xdcoutpost.xyz/XDC_Masternode_Rewards_Calculator/?utm_source=github)**

Part of [XDC Outpost](https://xdcoutpost.xyz/?utm_source=github-calculator) · Free, runs in your browser · ⭐ Star the repo if it helps you.

![XDC Masternode Epoch Rewards Calculator](XDC_Masternode_Rewards_Checker2.jpg)

## How it works

Epoch rewards aren't ordinary transactions, so the calculator **infers** them:

> **Epoch rewards = (balance at end − balance at start) − (transfers in − transfers out − gas fees)**

1. **Find the period's blocks.** It finds the first and last block of your period, in the time zone you choose.
2. **Read your balance** just before the start and at the end, from an XDC archive RPC.
3. **List your transactions** in that range from Etherscan (normal and internal), adding up transfers in, transfers out and gas fees. Failed transactions count their gas fee but not their value, since no XDC moved.
4. **Whatever the transactions don't explain** is counted as epoch rewards.

All maths is done in whole units (wei) with no rounding. Every figure is shown, and the full calculation log can be downloaded, so you or your accountant can check the working.

## How to use it

1. **Masternode owner address:** the wallet that staked the node (xdc… or 0x…), not the node's coinbase.
2. **Period:** pick dates, or use a quick button: last 30 days, last month, this year, last calendar year, or **last financial year (1 July to 30 June)**.
3. **Time zone:** starts as your device's time zone. The period runs from 00:00 on the start date to 23:59:59 on the end date in that zone, with daylight saving handled. Choose UTC to match tools that use UTC.
4. **Etherscan API key:** free, see below.
5. Click **Calculate epoch rewards**. A year usually takes under a minute.

The result shows the rewards total and a breakdown: balances, transfers, fees and the block range used. You can **copy a summary**, **download a CSV** for your records, or **download the full log**. Tick "Remember on this device" to save the address, key, time zone and RPC in your browser.

### Getting a free Etherscan API key

The calculator uses Etherscan's API to list your transactions. One free key covers XDC.

1. Sign up at [etherscan.io/register](https://etherscan.io/register).
2. Go to [etherscan.io/myapikey](https://etherscan.io/myapikey) and click **Add**.
3. Copy the key into the calculator.

The free plan is plenty: a calculation uses only a handful of requests. Keep your key private.

### Network settings

The default RPC is `https://rpc.ankr.com/xdc`. If you use your own, it must be an **archive node**, because the calculator reads balances at past blocks. A non-archive RPC gives an error saying so.

## Good to know

- **It's an inference.** Any other unexplained change in balance would also be counted as rewards. If a result looks wrong, check the log.
- **Native XDC only.** Token transfers aren't included.
- **Busy addresses work.** Long histories are fetched in batches, so addresses with more than 10,000 transactions in a period are fine.
- **Private:** the page talks directly to the RPC and Etherscan from your browser. Nothing is sent to XDC Outpost.

## Related tools

- [XDC Tycoon](https://github.com/s4njk4n/XDC_Tycoon): phone alerts for masternode status changes and reward payments.
- [XDC Sentinel](https://github.com/s4njk4n/XDC_Sentinel): phone alerts when a node goes offline.
- Need help running your nodes? See [installs and node care](https://github.com/s4njk4n/Plugin-XDC-Secure-RPC-WSS#done-for-you).

## Contact

Found a problem or have an idea? Open a [GitHub issue](https://github.com/s4njk4n/XDC_Masternode_Rewards_Calculator/issues), or message me on [Telegram](https://t.me/s4njk4n), Discord (@s4njk4n) or [X](https://x.com/s4njk4n).

[MIT License](LICENSE). Provided as-is, without warranty. Results are estimates for your information; check important figures, such as tax figures, with your accountant.

Transaction data powered by [Etherscan.io APIs](https://etherscan.io/apis).
