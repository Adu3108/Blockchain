# Simulation of a P2P Cryptocurrency Network and Adversial Attacks on the network

This repository contains the project done as a part of CS765: Introduction to Blockchains, Cryptocurrencies and Smart Contracts at IIT Bombay in Spring 2023. 

## Problem Statement 

This project aims to simulate a Discrete Event Blockchain Simulator for a P2P cryptocurrency network and study the effects of variation of several factors on the overall blockchain. We have considered the following factors :- 

1. **Number of peers**
  
2. **Percentage of users with low computational capacity**

3. **Percentage of users with better network connectivity**

4. **Mean interarrival time between transactions**

The second part of this project revolves around analyzing the impact of several adversial attacks on the blockchain. We have considered the following attacks in our analysis :- 

1. **Selfish Mining Attack**

A selfish miner (Adversary) keeps its discovered blocks private, thereby intentionally forking the chain. The honest nodes continue to mine on the public chain, while the adversary mines on its own private branch. If the adversary mines more blocks, it develops a longer lead over the public chain and continues to keep these new blocks private. When the public branch approaches the adversary’s private branch in length, it reveals blocks from its private chain to the public.

2. **Stubborn Mining Attack**

Similar to selfish mining attack, in stubborn mining, the adversary keeps its discovered blocks private. However, when the public branch approaches the adversary’s private branch in length then instead of revealing her entire private chain, the adversary reveals the next block on her private chain only to match the length of the public chain.

## Running the code

0. **Installing necessary packages**

  ```bash
  pip install -r requirements.txt
  ```
   
1. **Blockchain consisting of only honest miners**
   
   To simulate the P2P cryptocurrency network
   ```bash
   cd Honest
   python blockchain.py --n <No. of nodes> --z0 <Percentage of slow nodes> --z1 <Percentage of nodes with low CPU power> --ttx <Mean time of interarrival between transactions>
   ```

   To visualize the blockchain
   ```bash
   python visualize.py
   ```

2. **Blockchain consisting of an adversial miner**

   To simulate the P2P cryptocurrency network
   ```bash
   cd Adversial
   python blockchain.py --n <No. of nodes> --z0 <Percentage of slow nodes> --z1 <Percentage of nodes with low CPU power> --ttx <Mean time of interarrival between transactions> --tau <Percentage of nodes adversary is connected to> --hf <hashing power in percentage of adversary node>
   ```

   To visualize the blockchain
   ```bash
   python visualize.py
   ```
## Visualizing the Blockchain

These are some of the results obtained after visualizing the blockchain in different settings :- 

Blockchain with Honest Miner            |  Blockchain with an Adversial Miner
:-------------------------:|:-------------------------:
![resized](https://github.com/Adu3108/Blockchain/assets/81511060/52929f63-f2a1-4c8d-9de9-9d186010e7b0) | ![Blockchain_Node_0](https://github.com/Adu3108/Blockchain/assets/81511060/c5298186-7b63-47a6-a9a0-dea4a530fd49)

In the blockchain with an adversial miner, the red dot represents blocks mined by the attacker whereas the green dots represent blocks mined by honest miners.

## References

[Selfish Mining Attack](https://arxiv.org/abs/1311.0243)

[Stubborn Mining Attack](https://ieeexplore.ieee.org/abstract/document/7467362)

[Discrete Event Simulator](https://www.cs.cmu.edu/~music/cmsip/readings/intro-discrete-event-sim.html)
