## **Subscription Conversion**

		Journals

|journal_id|journal_date|journal_type|currency_id|journal_amt|customer_id|goal_id|goal_transaction_id|from_bank_account_id|from_bank_sub_account_id|to_bank_account_id|to_bank_sub_account_id|bank_ref|retry_ct|status|broker_id|
|----------|------------|------------|-----------|-----------|-----------|-------|-------------------|--------------------|------------------------|------------------|----------------------|--------|--------|------|---------|
|800100000421|2023-12-05 06:15:49.000|SUBSCRIPTION_CONVERSION|SAR|1000|1046500003|GOAL00000003|TRAN00000043|WALLETPOOLSAR|WALLETPOOLSAR1046500003|WALLETPOOLUSD|WALLETPOOLUSD1046500003|72b94e0f-8944-4243-aa24-67dd97aad570|1|POSTED|ALPACASECU|

		Bank Entry

|entry_id|bank_account_id|bank_sub_account_id|posting_date|posting_desc|posting_type|currency_id|posting_amt|goal_transaction_id|bank_journal_id|broker_remittance_id|bank_ref|bank_running_balance_amt|status|goal_id|is_bank_statement_matched|goal_transaction_type|is_remittance_matched|wallet_pool_id|wallet_payment_id|
|--------|---------------|-------------------|------------|------------|------------|-----------|-----------|-------------------|---------------|--------------------|--------|------------------------|------|-------|-------------------------|---------------------|---------------------|--------------|-----------------|
|BACE00000241|WALLETPOOLSAR|WALLETPOOLSAR1046500003|2023-12-05 06:43:57.000||WITHDRAWAL|SAR|1000|TRAN00000043|800100000421||||POSTED|||SUBSCRIPTION||||
|BACE00000242|WALLETPOOLUSD|WALLETPOOLUSD1046500003|2023-12-05 06:43:57.000||DEPOSIT|USD|266.67|TRAN00000043|800100000421||||POSTED|||SUBSCRIPTION||||


## **Subscription Consolidation**

		Journals

|journal_id|journal_date|journal_type|currency_id|journal_amt|customer_id|goal_id|goal_transaction_id|from_bank_account_id|from_bank_sub_account_id|to_bank_account_id|to_bank_sub_account_id|bank_ref|retry_ct|status|broker_id|
|----------|------------|------------|-----------|-----------|-----------|-------|-------------------|--------------------|------------------------|------------------|----------------------|--------|--------|------|---------|
|800100000441|2023-12-05 06:46:56.000|SUBSCRIPTION_CONSOLIDATION|USD|266.67|1046500003|GOAL00000003|TRAN00000043|WALLETPOOLUSD|WALLETPOOLUSD1046500003|ALPACASECUUSD||763af99a-044e-4eb5-bab5-b36200dca284|1|POSTED|ALPACASECU|

		Bank Entry

|entry_id|bank_account_id|bank_sub_account_id|posting_date|posting_desc|posting_type|currency_id|posting_amt|goal_transaction_id|bank_journal_id|broker_remittance_id|bank_ref|bank_running_balance_amt|status|goal_id|is_bank_statement_matched|goal_transaction_type|is_remittance_matched|wallet_pool_id|wallet_payment_id|
|--------|---------------|-------------------|------------|------------|------------|-----------|-----------|-------------------|---------------|--------------------|--------|------------------------|------|-------|-------------------------|---------------------|---------------------|--------------|-----------------|
|BACE00000243|WALLETPOOLUSD|WALLETPOOLUSD1046500003|2023-12-05 06:47:04.000||WITHDRAWAL|USD|266.67|TRAN00000043|800100000441||||POSTED|||SUBSCRIPTION||||
|BACE00000244|ALPACASECUUSD||2023-12-05 06:47:04.000||DEPOSIT|USD|266.67|TRAN00000043|800100000441||||POSTED|||SUBSCRIPTION||||

## **Subscription Remittance**

|broker_remittance_id|broker_id|remittance_date|remittance_type|remittance_currency_id|remittance_amt|broker_ref|retry_ct|status|bank_ref|
|--------------------|---------|---------------|---------------|----------------------|--------------|----------|--------|------|--------|
|900100000241|ALPACASECU|2023-12-05 06:51:38.000|OUTWARD|USD|266.67||1|REMITTED|763af99a-044e-4eb5-bab5-b36200dca284|





