# chainlink-manager
script(s) used to help manage chainlink nodes on a single host
---

#### This has been tested on Debian 10 & 11.

(use at your own risk, consider this as 100% untested)

---
## General Directions
* Update the ```./networks/$NETWORK_MAINNET``` file(s) with the values specific to each of your Chainlink Nodes
* Use this script to deploy and upgrade your Chainlink Nodes.

---

## Utilization
### Initialize a New Docker Environment for Chainlink External Adapters
#### NOTE: This is not currently working.
* This will:
  * Install Docker-CE if it is not already installed.
  * Deploy a Postgres container for your Chainlink Nodes.
  * Deploy a Chainlink Node for the specified network.

```bash
sudo ./cl-manager -i
```


--
### Deploy New External Adapter With Specific Version
* This will:
  * Deploy a new Chainlink Node of the desired release.

```bash
./cl-manager -d ocr-arbitrum-mainnet 1.3.0
```


--
### Upgrade an Existing Chainlink Node
* This will:
  * Stop the current Chainlink container(s).
  * Remove the Chainlink container(s).
  * Deploy a new Chainlink container(s) based on the desired image version.

```bash
./cl-manager -u ocr-arbitrum-mainnet 1.3.0
```
```bash
./cl-manager -u all 1.3.0
```


--
### List all Supported Networks
* This will:
  * List all networks supported by the script

```bash
./cl-manager -l
```


--
### List all Chainlink Node Containers
* This will:
  * Print a pretty formatted list of all your Chainlink Nodes and which ports they're listening on

```bash
./cl-manager -s
```


--
