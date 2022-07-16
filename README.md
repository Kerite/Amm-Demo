```shell
near view kerite.testnet get_balance_a
near view kerite.testnet get_balance_b

near call test-token-a.testnet storage_deposit --accountId kerite.testnet --amount 0.00125
near call test-token-a.testnet ft_transfer '{"receiver_id": "kerite.testnet", "amount": "200"}' --accountId test-token-a.testnet --depositYocto 1
near call kerite.testnet add_liquidity '{"token": "test-token-a.testnet", "amount_in": 200}' --accountId keriteal.testnet

near call test-token-b.testnet storage_deposit --accountId kerite.testnet --amount 0.00125
near call test-token-b.testnet ft_transfer '{"receiver_id": "kerite.testnet", "amount": "2000"}' --accountId test-token-b.testnet --depositYocto 1
near call kerite.testnet add_liquidity '{"token": "test-token-b.testnet", "amount_in": 2000}' --accountId keriteal.testnet

near call test-token-a.testnet storage_deposit --accountId user-test-amm-1.testnet --amount 0.00125
near call test-token-b.testnet storage_deposit --accountId user-test-amm-1.testnet --amount 0.00125

near call test-token-b.testnet ft_transfer '{"receiver_id": "kerite.testnet", "amount": "40"}' --accountId test-token-b.testnet --depositYocto 1
near call kerite.testnet swap '{"token_in": "test-token-b.testnet", "amount_in": 40}' --accountId user-test-amm-1.testnet --depositYocto 1
```
