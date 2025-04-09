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
# Assignment 
Installation of IPFS on local machine. Further, upload the files (such as photos, audio, and video) on IPFS and share it with other through content identifier (i.e., hash). Perform assessment using ubuntu WSL.


## Step 1: Install IPFS on Ubuntu WSL

1. Download IPFS:
   ```
   wget https://dist.ipfs.tech/kubo/v0.34.1/kubo_v0.34.1_linux-amd64.tar.gz
   ```
![imag5](https://github.com/kushkumarkashyap7280/Blockchain/blob/7c54a25eeeb1e0ec6ff5e12aad36d6ff3953a52f/till%20install.sh%202.jpg)
2. Extract the archive:
   ```
   tar -xvzf kubo_v0.34.1_linux-amd64.tar.gz
   ```

3. Change directory:
   ```
   cd kubo
   ```

4. Install IPFS:
   ```
   sudo bash install.sh
   ```

5. Check IPFS version:
   ```
   ipfs --version
   ```

6. Initialize IPFS:
   ```
   ipfs init
   ```

7. Start IPFS daemon in the background:
   ```
   ipfs daemon > ipfs.log 2>&1 &
   ```
![imag6](https://github.com/kushkumarkashyap7280/Blockchain/blob/e3c9e76cc9e56cc45fa897a9f69f3f04a39089fc/ipfs%20dashboard.jpg)
8. Confirm daemon is running:
   ```
   ps aux | grep ipfs
   ```



## Step 2: Upload Files to IPFS

1. TEXT file  hello.txt.
   ```
   Add file: echo "Hello, IPFS!" > hello.txt
   ```
2. add 
   ```
   ipfs add hello.txt
   ```

3. to see on IPFS
   ```
   ipfs files cp /ipfs/QmWd9cavD8UGZQcqYBVhZqs2Jure5W9cgxR7S6TC4StfZe /hello.txt
   ```
4. To see your file using content id.
   ```
   ipfs cat <CID>
   ```
   ![imag7](https://github.com/kushkumarkashyap7280/Blockchain/blob/e3c9e76cc9e56cc45fa897a9f69f3f04a39089fc/hello.txt%20added%20to%20ipfs.jpg)

5. Add a directory:
   ```
   mkdir myfolder
   echo "File 1 content" > myfolder/file1.txt
   echo "File 2 content" > myfolder/file2.txt
    ipfs add -r myfolder
   ipfs files cp /ipfs/QmYGnc2YNxkhQG37H1HhiJacskSS79oCHYBCBDa3NncFqG /myfolder
   ```
   ![imag7](https://github.com/kushkumarkashyap7280/Blockchain/blob/e3c9e76cc9e56cc45fa897a9f69f3f04a39089fc/myfolder.jpg)
    ![imag18](https://github.com/kushkumarkashyap7280/Blockchain/blob/e3c9e76cc9e56cc45fa897a9f69f3f04a39089fc/my%20folder%20files.jpg)

6. Upload a sample video:
   ```
   ipfs add sample.mp4
    ipfs files cp /ipfs/<CID>/sample.mp4
   ```
     ![imag19](https://github.com/kushkumarkashyap7280/Blockchain/blob/e3c9e76cc9e56cc45fa897a9f69f3f04a39089fc/sample.mp4%20in%20ubuntu.jpg)

7. Output after upload:
   ```
   added <CID> sample.mp4
   ```
   ![imag20](https://github.com/kushkumarkashyap7280/Blockchain/blob/e3c9e76cc9e56cc45fa897a9f69f3f04a39089fc/sample%20video%20added.jpg)
## Step 3: Share File using CID

The video file can be shared with others using the following IPFS link:
   ![imag21](https://github.com/kushkumarkashyap7280/Blockchain/blob/e3c9e76cc9e56cc45fa897a9f69f3f04a39089fc/share%20video%20file.jpg)



Anyone with the link can view or download the video directly from the IPFS network.

## Step 4: To stop it, simply run:

   ```
  kill <PID>
   ```
  Then, to confirm it stopped:
 ```
  ps aux | grep ipfs
   ```

