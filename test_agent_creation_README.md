# Steps to create a test example using the projnanda repo

## Prerequisites
Before running the SDK, setup the following:

### 1. AWS account with a EC2 Linux instance
Create an [AWS account](https://aws.amazon.com). Create a EC2 Linux instance and during creation make a network security group that allows the following ports: 22 (SSH), 80 (HTTP), 443 (HTTPS), 3000 (custom TCP), 5001 (custom TCP), 600-6200 (custom TCP), 8080 (custom TCP), 6900 (custom TCP). Create a key pair and save the .pem file locally.

### 2. Create a domain name
Register a domain name (e.g. test_domain.com) via Namecheap, GoDaddy, etc. In the domain's DNS settings, create an "A" record that points the domain name to your EC2 instance's public IPv4 address.

### 3. Anthropic account with API key
Create an [anthropic account](https://www.anthropic.com) and generate API key. Keep track of this key.

## Create a test example

### 1. Clone this repository

> git clone github.com/LaurenDiana16/nanda-adapter-sdk

### 2. Create a python3 virtual environment and activate it

> python3 -m venv environments/venv

> source environments/venv/bin/activate

### 3. Setup dependencies

> cd nanda_agent/examples

> pip install -r requirements.txt

### 4. Move certificates into current path

> cp <location of .pem file> ./fullchain.pem
> cp <location of .pem file> ./privkey.pem

### 5. Set your enviroment variables (ANTHROPIC_API_KEY, DOMAIN_NAME)

> export ANTHROPIC_API_KEY="your-api-key-here"

> export DOMAIN_NAME="<YOUR_DOMAIN_NAME.COM>"

### 6. Run an example agent (langchain_pirate.py)

> nohup python3 langchain_pirate.py > out.log 2>&1 &

### 7. Get your enrollment link from Log File

> cat out.log