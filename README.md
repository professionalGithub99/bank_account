# Bank Account Canister 

A sample bank account canister created by Albert Du demonstrating simple transfer, account query balance, blob to hex transformations, etc.

## Deploying Locally

Follow steps 3-10 for the ledger canister https://github.com/dfinity/ic/blob/master/rs/rosetta-api/ledger_canister/README.md

Then run
```bash
dfx deploy bank_account
```

##Running the code

View your account id blob using 
```bash
dfx canister call bank_account get_self_account_id
```
It will come out in the frormat like blob "a43\a4\b4\c6....."

Now transfer yourself some icyps with 

```bash
dfx canister call ledger transfer '(record {memo=1;amount=record {e8s=30000}; fee=record {e8s=10000};from_subaccount=null;to= <blob-from last step>;created_at_time=null})'
```
replace the  <blob-from last step>=blob "a43\a4\b4\c6....." exactly with the blob the string 

View your the canister principal id with

```bash
dfx identity principal-id
```
You should get some format like principal "abkcw-sjkjblj-sjskl..."

now view the bank account balance with 
```bash
dfx canister call bank_account get_balance '(<that-principal>)'
```
again replace the full format <that-prinicpal>= principal "abkcw-sjkjblj-sjskl..." 

You should have some icyps!




