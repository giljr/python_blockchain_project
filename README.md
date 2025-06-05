### 🧱 Simple Blockchain with Transactions in Python

A minimal blockchain implementation in Python featuring transaction support, Proof of Work, and a RESTful API powered by Flask.

### 🚀 Features
```

Blockchain data structure with block linking via hashes.

Simple Proof of Work (PoW) algorithm.

Transaction pool integrated into mined blocks.

RESTful API with endpoints to mine, view the chain, validate it, and add transactions.
```
Demonstrates fundamental blockchain concepts.

#### 📝 Key Endpoints

Endpoint	Method	Description
```
/mine_block	        GET	Mines a new block and adds it to chain
/get_chain	        GET	Retrieves the full blockchain
/is_valid	        GET	Validates the blockchain integrity
/add_transaction	POST	Adds a new transaction
```
#### 🛠️ How It Works
Blockchain Structure
Each block contains:
```
index

timestamp

proof (Proof of Work)

previous_hash
```
#### transactions ✅

Transactions
```
Added via /add_transaction.
```
Stored in a pending transaction pool.

Included in the next mined block.

#### Proof of Work
Simple algorithm finding a number such that:
```
SHA256(new_proof² - previous_proof²) → hash starts with '00000'.
```
#### Validation
Ensures each block's hash correctly references its predecessor and PoW is valid.

#### ▶️ Getting Started
Clone the repo:
```
git clone https://github.com/yourusername/blockchain-python.git
cd blockchain-python
```
Install dependencies:

```python

pip install flask
```
Run the Flask app:

```python
python blockchain.py
```

Access API at:

http://127.0.0.1:5000

#### 📦 Example Usage
Add a transaction:
```curl
curl -X POST -H "Content-Type: application/json" \
-d '{"sender": "Alice", "recipient": "Bob", "amount": 50}' \
http://127.0.0.1:5000/add_transaction
```
Mine a block:
```curl
curl http://127.0.0.1:5000/mine_block
```
Check the chain:
```curl
curl http://127.0.0.1:5000/get_chain
```
🖼️ Blockchain Flow
```plaintext
[User Input]
  ↓
new_transaction(sender, recipient, amount)
  ↓
[Transactions Pool]
  ↓
mine_block()
  ↓
[Proof of Work]
  ↓
[create_block(proof, previous_hash, transactions)]
  ↓
[Append to Chain]
  ↓
[Clear Transactions]
```
#### 🧪 Testing with Postman
Open Postman → New → HTTP Request.

Set method to POST.

URL: http://127.0.0.1:5000/add_transaction.

Body → raw → JSON:
```plaintext
{
  "sender": "Alice",
  "recipient": "Bob",
  "amount": 50
}
```
#### ❓ Need Help?
If you get stuck, please refer to my [page](https://medium.com/jungletronics/building-a-simple-blockchain-with-python-and-flask-a95da7b5b713).

#### 🏁 Summary
✅ Blockchain implemented from scratch.

✅ Transactions added to blocks.

✅ Simple Proof of Work.

✅ REST API via Flask.

✅ Testing with curl or Postman.



## License

[MIT](https://choosealicense.com/licenses/mit/)

