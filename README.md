# Blockchain

## Hyperledger Fabric test network

---

## 1. Install Go (Golang)

Golang is a required dependency for running Hyperledger Fabric.

```bash
sudo apt install golang-go
```

---

## 2. Check Docker Installation

Docker is needed to run Fabric components as containers. Verify it's installed:

```bash
docker --version
```

---

## 3. Check Docker Compose Installation

Docker Compose is used to manage multi-container applications like Fabric.

```bash
docker-compose --version
```

---

## 4. List the Files in the Current Directory

Just to verify where you are.

```bash
ls
```

---

## 5. Clone the Hyperledger Fabric Samples Repository

This repository contains example configurations and network setups.

```bash
git clone -b main https://github.com/hyperledger/fabric-samples.git
```

---

## 6. Change into the Fabric Samples Directory

Move into the directory you just cloned.

```bash
cd fabric-samples
```

---

## 7. Download the Binaries and Docker Images

This command fetches the necessary binaries and Docker images for Fabric.

```bash
curl -sSL https://bit.ly/2ysbOFE | bash -s
```

---

## 8. Navigate to the Test Network Directory

This directory contains scripts to bring up a sample Fabric network.

```bash
cd test-network
```
![img1](https://github.com/kushkumarkashyap7280/Blockchain/blob/92cc5a16e611d6347d63076adf013ccfda5200c3/cd%20fabric%20sample.jpg )

---

## 9.

```bash
./network.sh
```

---

## 10. start the Test Network

This will start a basic Fabric network with two organizations and their peers.

```bash
./network.sh up
```
![img2 ](https://github.com/kushkumarkashyap7280/Blockchain/blob/92cc5a16e611d6347d63076adf013ccfda5200c3/network%20started.jpg)
---

## 11. Create a Channel

Once the network is up, create a channel to allow communication between peers.

```bash
./network.sh createChannel
```
![img3](https://github.com/kushkumarkashyap7280/Blockchain/blob/92cc5a16e611d6347d63076adf013ccfda5200c3/channel%20created.jpg)
---

## 12. Shut Down the Network

When  done, tear down the running network to free resources.

```bash
./network.sh down
```
![imag4](https://github.com/kushkumarkashyap7280/Blockchain/blob/92cc5a16e611d6347d63076adf013ccfda5200c3/down%20network.jpg)
---

