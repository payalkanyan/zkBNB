# zkBNB

## Overview

Contract Address deployed : https://testnet.bscscan.com/address/0xe4aa8a4b22b4426d8269fb85ed83474a3386d4b1

In the digital age, the authenticity of content on social media is paramount. This project introduces a novel approach by integrating Zero-Knowledge Machine Learning (ZKML) into social media interactions. Users are prompted to select a sentiment tag for their content and generate a proof that it aligns with the chosen sentiment. With ZKML verification, only genuine content is published, ensuring a true and honest representation of sentiments. 

## Features

- **Sentiment Tagging**: Users select a sentiment that matches their content's essence.
  
- **Proof Generation & Verification**: Before publishing, users generate a proof that their content aligns with the chosen sentiment. Only content passing the ZKML verification process is published.
  
- **Content Filtering**: Option to filter out content tagged as sensitive, ensuring user comfort.

## How It Works

### 1. Machine Learning Model

The project began with training a machine learning model using PyTorch. The dataset used is available on [Kaggle](https://www.kaggle.com/datasets/kazanova/sentiment140). The generated files `word_to_index.json` and `index_to_word.json` enable text-to-index conversion, vital as ML models cannot directly process strings. These files are hosted on Filecoin.

### 2. Zero-Knowledge Programming

The model's weights and biases were exported for integration into Noir, Aztec's Zero-Knowledge programming language. The noir-ml library was used is on this [link](https://github.com/metavind/noir-ml/tree/main/noir_ml). Circuit and model are transparently hosted on Filecoin.

### 3. Circuit Transformation & Integration

Using the `nargo` tool, the circuit was converted into Solidity Verifier code. This verifier is integrated into core Solidity code functions like posts, comments, and likes. 

### 4. Frontend & Backend

The frontend, developed using React and Ethers, serves as the user interface. Before posting, users validate their content's alignment with their chosen sentiment tag. The backend manages sentence-to-index conversions, proof generation, and verification.

