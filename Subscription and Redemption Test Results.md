# Subscription

### POST Goal Transaction 
		Goal Transaction Request body
```
{
  "transaction_type": "SUBSCRIPTION",
  "transaction_sub_type": "",
  "transaction_amt": 1000,
  "transaction_currency_id": "SAR",
  "customer_id": "1046500003",
  "goal_id": "GOAL00000003"
}

```
		 Goal Transaction Table

|goal_transaction_id|transaction_type|transaction_date|transaction_amt|investment_account_id|customer_id|goal_id|status|broker_id|broker_remittance_id|transaction_sub_type|consolidation_amt|conversion_amt|order_amt|transaction_currency_id|conversion_currency_id|consolidation_currency_id|order_currency_id|transfer_amt|transfer_currency_id|remittance_amt|remittance_currency_id|distribution_amt|distribution_currency_id|transaction_sar_amount|transaction_usd_amount|
|-------------------|----------------|----------------|---------------|---------------------|-----------|-------|------|---------|--------------------|--------------------|-----------------|--------------|---------|-----------------------|----------------------|-------------------------|-----------------|------------|--------------------|--------------|----------------------|----------------|------------------------|----------------------|----------------------|
|TRAN00000101|SUBSCRIPTION|2023-12-16 06:44:55.000|1000|ALPACASECU1046500003|1046500003|GOAL00000003|CREATED|ALPACASECU|||0|0|0|SAR||||0||0||0||1000|266.6667|

-------------------------------------------------------------------------------
### Subscription Conversion

#### Initiate 

		 Goal Transaction Table

|goal_transaction_id|transaction_type|transaction_date|transaction_amt|investment_account_id|customer_id|goal_id|status|broker_id|broker_remittance_id|transaction_sub_type|consolidation_amt|conversion_amt|order_amt|transaction_currency_id|conversion_currency_id|consolidation_currency_id|order_currency_id|transfer_amt|transfer_currency_id|remittance_amt|remittance_currency_id|distribution_amt|distribution_currency_id|transaction_sar_amount|transaction_usd_amount|
|-------------------|----------------|----------------|---------------|---------------------|-----------|-------|------|---------|--------------------|--------------------|-----------------|--------------|---------|-----------------------|----------------------|-------------------------|-----------------|------------|--------------------|--------------|----------------------|----------------|------------------------|----------------------|----------------------|
|TRAN00000101|SUBSCRIPTION|2023-12-16 06:44:55.000|1000|ALPACASECU1046500003|1046500003|GOAL00000003|CONVERSION_INITIATED|ALPACASECU|||0|0|0|SAR||||0||0||0||1000|266.67|

		 Bank Account 

|bank_account_id|bank_account_num|bank_account_iban|bank_account_name|bank_id|bank_account_type|currency_id|balance_amt|available_amt|bank_balance_amt|broker_id|payment_channel_id|wallet_pool_id|status|bank_statement_offset|
|---------------|----------------|-----------------|-----------------|-------|-----------------|-----------|-----------|-------------|----------------|---------|------------------|--------------|------|---------------------|
|WALLETPOOLSAR|0108065554100010|SA9230400108065554100010||ARNBSARI|WALLET_POOL|SAR|3090|2090|3090|ALPACASECU||WALLETPOOLSAR|ACTIVE||
|WALLETPOOLUSD|0108052004590026|SA2730400108052004590026||ARNBSARI|WALLET_POOL|USD|9263.22|8996.55|8996.55|ALPACASECU||WALLETPOOLUSD|ACTIVE||

		 Bank Sub Account

|bank_sub_account_id|bank_account_num|bank_account_iban|bank_account_name|bank_id|bank_account_id|currency_id|balance_amt|available_amt|customer_id|status|wallet_pool_id|bank_statement_offset|bank_balance_amt|
|-------------------|----------------|-----------------|-----------------|-------|---------------|-----------|-----------|-------------|-----------|------|--------------|---------------------|----------------|
|WALLETPOOLSAR1046500003|0108055667680369|SA1130400108055667680369|Sulaiman|ARNBSARI|WALLETPOOLSAR|SAR|3090|2090|1046500003|ACTIVE|WALLETPOOLSAR||3090|
|WALLETPOOLUSD1046500003|0108095164500016|SA1830400108095164500016|Sulaiman|ARNBSARI|WALLETPOOLUSD|USD|9060.22|8793.55|1046500003|ACTIVE|WALLETPOOLUSD||8793.55|

		 Bank Journal

|journal_id|journal_date|journal_type|currency_id|journal_amt|customer_id|goal_id|goal_transaction_id|from_bank_account_id|from_bank_sub_account_id|to_bank_account_id|to_bank_sub_account_id|bank_ref|retry_ct|status|broker_id|
|----------|------------|------------|-----------|-----------|-----------|-------|-------------------|--------------------|------------------------|------------------|----------------------|--------|--------|------|---------|
|800100000461|2023-12-16 12:22:01.000|SUBSCRIPTION_CONVERSION|SAR|1000|1046500003|GOAL00000003|TRAN00000101|WALLETPOOLSAR|WALLETPOOLSAR1046500003|WALLETPOOLUSD|WALLETPOOLUSD1046500003||0|CREATED|ALPACASECU|

#### Request 

		 Bank Journal

|journal_id|journal_date|journal_type|currency_id|journal_amt|customer_id|goal_id|goal_transaction_id|from_bank_account_id|from_bank_sub_account_id|to_bank_account_id|to_bank_sub_account_id|bank_ref|retry_ct|status|broker_id|
|----------|------------|------------|-----------|-----------|-----------|-------|-------------------|--------------------|------------------------|------------------|----------------------|--------|--------|------|---------|
|800100000461|2023-12-16 12:22:01.000|SUBSCRIPTION_CONVERSION|SAR|1000|1046500003|GOAL00000003|TRAN00000101|WALLETPOOLSAR|WALLETPOOLSAR1046500003|WALLETPOOLUSD|WALLETPOOLUSD1046500003|58c05596-f2a0-4d3f-b182-b0daa864fe02|1|REQUESTED|ALPACASECU|


Other tables are in same state as in conversion initiate

#### Status

		Bank Journal

|journal_id|journal_date|journal_type|currency_id|journal_amt|customer_id|goal_id|goal_transaction_id|from_bank_account_id|from_bank_sub_account_id|to_bank_account_id|to_bank_sub_account_id|bank_ref|retry_ct|status|broker_id|
|----------|------------|------------|-----------|-----------|-----------|-------|-------------------|--------------------|------------------------|------------------|----------------------|--------|--------|------|---------|
|800100000461|2023-12-16 12:22:01.000|SUBSCRIPTION_CONVERSION|SAR|1000|1046500003|GOAL00000003|TRAN00000101|WALLETPOOLSAR|WALLETPOOLSAR1046500003|WALLETPOOLUSD|WALLETPOOLUSD1046500003|58c05596-f2a0-4d3f-b182-b0daa864fe02|1|POSTED|ALPACASECU|

		 Goal Transaction

|goal_transaction_id|transaction_type|transaction_date|transaction_amt|investment_account_id|customer_id|goal_id|status|broker_id|broker_remittance_id|transaction_sub_type|consolidation_amt|conversion_amt|order_amt|transaction_currency_id|conversion_currency_id|consolidation_currency_id|order_currency_id|transfer_amt|transfer_currency_id|remittance_amt|remittance_currency_id|distribution_amt|distribution_currency_id|transaction_sar_amount|transaction_usd_amount|
|-------------------|----------------|----------------|---------------|---------------------|-----------|-------|------|---------|--------------------|--------------------|-----------------|--------------|---------|-----------------------|----------------------|-------------------------|-----------------|------------|--------------------|--------------|----------------------|----------------|------------------------|----------------------|----------------------|
|TRAN00000101|SUBSCRIPTION|2023-12-16 06:44:55.000|1000|ALPACASECU1046500003|1046500003|GOAL00000003|CONVERSION_DONE|ALPACASECU|||0|266.67|0|SAR|USD|||0||0||0||1000|266.67|

		 Bank Account

|bank_account_id|bank_account_num|bank_account_iban|bank_account_name|bank_id|bank_account_type|currency_id|balance_amt|available_amt|bank_balance_amt|broker_id|payment_channel_id|wallet_pool_id|status|bank_statement_offset|
|---------------|----------------|-----------------|-----------------|-------|-----------------|-----------|-----------|-------------|----------------|---------|------------------|--------------|------|---------------------|
|WALLETPOOLSAR|0108065554100010|SA9230400108065554100010||ARNBSARI|WALLET_POOL|SAR|2090|2090|3090|ALPACASECU||WALLETPOOLSAR|ACTIVE||
|WALLETPOOLUSD|0108052004590026|SA2730400108052004590026||ARNBSARI|WALLET_POOL|USD|9263.22|9263.22|8996.55|ALPACASECU||WALLETPOOLUSD|ACTIVE||

		 Bank Sub Account

|bank_sub_account_id|bank_account_num|bank_account_iban|bank_account_name|bank_id|bank_account_id|currency_id|balance_amt|available_amt|customer_id|status|wallet_pool_id|bank_statement_offset|bank_balance_amt|
|-------------------|----------------|-----------------|-----------------|-------|---------------|-----------|-----------|-------------|-----------|------|--------------|---------------------|----------------|
|WALLETPOOLSAR1046500003|0108055667680369|SA1130400108055667680369|Sulaiman|ARNBSARI|WALLETPOOLSAR|SAR|2090|2090|1046500003|ACTIVE|WALLETPOOLSAR||3090|
|WALLETPOOLUSD1046500003|0108095164500016|SA1830400108095164500016|Sulaiman|ARNBSARI|WALLETPOOLUSD|USD|9060.22|9060.22|1046500003|ACTIVE|WALLETPOOLUSD||8793.55|

		 Bank Entry

|entry_id|bank_account_id|bank_sub_account_id|posting_date|posting_desc|posting_type|currency_id|posting_amt|goal_transaction_id|bank_journal_id|broker_remittance_id|bank_ref|bank_running_balance_amt|status|goal_id|is_bank_statement_matched|goal_transaction_type|is_remittance_matched|wallet_pool_id|wallet_payment_id|
|--------|---------------|-------------------|------------|------------|------------|-----------|-----------|-------------------|---------------|--------------------|--------|------------------------|------|-------|-------------------------|---------------------|---------------------|--------------|-----------------|
|BACE00000341|WALLETPOOLSAR|WALLETPOOLSAR1046500003|2023-12-18 10:29:56.000||WITHDRAWAL|SAR|1000|TRAN00000101|800100000461||||POSTED|||SUBSCRIPTION||||
|BACE00000342|WALLETPOOLUSD|WALLETPOOLUSD1046500003|2023-12-18 10:29:57.000||DEPOSIT|USD|266.67|TRAN00000101|800100000461||||POSTED|||SUBSCRIPTION||||


		 Goal

|goal_id|customer_id|goal_name|goal_name_ar|target_sar_amt|start_date|end_date|duration_months|balance_sar_amt|interim_usd_amt|recurring_sar_amt|recurring_next_date|portfolio_id|status|risk_level|initial_sar_amt|investment_balance_amt|investment_available_amt|transit_usd_amt|investment_account_id|broker_id|investment_currency_id|expected_roi_sar_amt|portfolio_changed_date|
|-------|-----------|---------|------------|--------------|----------|--------|---------------|---------------|---------------|-----------------|-------------------|------------|------|----------|---------------|----------------------|------------------------|---------------|---------------------|---------|----------------------|--------------------|----------------------|
|GOAL00000003|1046500003|New Car||0|2023-01-01 05:30:00.000|2024-12-30 05:30:00.000|0|0|266.67|0|2024-06-30 05:30:00.000|25acf30f-99b0-4745-8d54-27751904216a|ACTIVE||0|0|0|0||||||

-------------------------------------------------------------------------------

### Subscription Consolidation

#### Initiate 

		 Goal Transaction

|goal_transaction_id|transaction_type|transaction_date|transaction_amt|investment_account_id|customer_id|goal_id|status|broker_id|broker_remittance_id|transaction_sub_type|consolidation_amt|conversion_amt|order_amt|transaction_currency_id|conversion_currency_id|consolidation_currency_id|order_currency_id|transfer_amt|transfer_currency_id|remittance_amt|remittance_currency_id|distribution_amt|distribution_currency_id|transaction_sar_amount|transaction_usd_amount|
|-------------------|----------------|----------------|---------------|---------------------|-----------|-------|------|---------|--------------------|--------------------|-----------------|--------------|---------|-----------------------|----------------------|-------------------------|-----------------|------------|--------------------|--------------|----------------------|----------------|------------------------|----------------------|----------------------|
|TRAN00000101|SUBSCRIPTION|2023-12-16 06:44:55.000|1000|ALPACASECU1046500003|1046500003|GOAL00000003|CONSOLIDATION_INITIATED|ALPACASECU|||0|266.67|0|SAR|USD|||0||0||0||1000|266.67|

		 Bank Account

|bank_account_id|bank_account_num|bank_account_iban|bank_account_name|bank_id|bank_account_type|currency_id|balance_amt|available_amt|bank_balance_amt|broker_id|payment_channel_id|wallet_pool_id|status|bank_statement_offset|
|---------------|----------------|-----------------|-----------------|-------|-----------------|-----------|-----------|-------------|----------------|---------|------------------|--------------|------|---------------------|
|WALLETPOOLSAR|0108065554100010|SA9230400108065554100010||ARNBSARI|WALLET_POOL|SAR|2090|2090|3090|ALPACASECU||WALLETPOOLSAR|ACTIVE||
|WALLETPOOLUSD|0108052004590026|SA2730400108052004590026||ARNBSARI|WALLET_POOL|USD|9263.22|8996.55|8996.55|ALPACASECU||WALLETPOOLUSD|ACTIVE||
|ALPACASECUUSD|0108020000010015|SA5330400108020000010015||ARNBSARI|BROKER|USD|266.67|0|30373.13|ALPACASECU|||ACTIVE||

		 Bank Sub Account

|bank_sub_account_id|bank_account_num|bank_account_iban|bank_account_name|bank_id|bank_account_id|currency_id|balance_amt|available_amt|customer_id|status|wallet_pool_id|bank_statement_offset|bank_balance_amt|
|-------------------|----------------|-----------------|-----------------|-------|---------------|-----------|-----------|-------------|-----------|------|--------------|---------------------|----------------|
|WALLETPOOLSAR1046500003|0108055667680369|SA1130400108055667680369|Sulaiman|ARNBSARI|WALLETPOOLSAR|SAR|2090|2090|1046500003|ACTIVE|WALLETPOOLSAR||3090|
|WALLETPOOLUSD1046500003|0108095164500016|SA1830400108095164500016|Sulaiman|ARNBSARI|WALLETPOOLUSD|USD|9060.22|8793.55|1046500003|ACTIVE|WALLETPOOLUSD||8793.55|

		Bank Journal

|journal_id|journal_date|journal_type|currency_id|journal_amt|customer_id|goal_id|goal_transaction_id|from_bank_account_id|from_bank_sub_account_id|to_bank_account_id|to_bank_sub_account_id|bank_ref|retry_ct|status|broker_id|
|----------|------------|------------|-----------|-----------|-----------|-------|-------------------|--------------------|------------------------|------------------|----------------------|--------|--------|------|---------|
|800100000481|2023-12-18 10:43:03.000|SUBSCRIPTION_CONSOLIDATION|USD|266.67|1046500003|GOAL00000003|TRAN00000101|WALLETPOOLUSD|WALLETPOOLUSD1046500003|ALPACASECUUSD|||0|CREATED|ALPACASECU|

#### Request

		 Bank Journal

|journal_id|journal_date|journal_type|currency_id|journal_amt|customer_id|goal_id|goal_transaction_id|from_bank_account_id|from_bank_sub_account_id|to_bank_account_id|to_bank_sub_account_id|bank_ref|retry_ct|status|broker_id|
|----------|------------|------------|-----------|-----------|-----------|-------|-------------------|--------------------|------------------------|------------------|----------------------|--------|--------|------|---------|
|800100000481|2023-12-18 10:43:03.000|SUBSCRIPTION_CONSOLIDATION|USD|266.67|1046500003|GOAL00000003|TRAN00000101|WALLETPOOLUSD|WALLETPOOLUSD1046500003|ALPACASECUUSD||0d5712ac-48ab-42fe-974a-506440f70540|1|REQUESTED|ALPACASECU|

Other tables are in same state as in Consolidation initiate

#### Status

		Bank Journal

|journal_id|journal_date|journal_type|currency_id|journal_amt|customer_id|goal_id|goal_transaction_id|from_bank_account_id|from_bank_sub_account_id|to_bank_account_id|to_bank_sub_account_id|bank_ref|retry_ct|status|broker_id|
|----------|------------|------------|-----------|-----------|-----------|-------|-------------------|--------------------|------------------------|------------------|----------------------|--------|--------|------|---------|
|800100000481|2023-12-18 10:43:03.000|SUBSCRIPTION_CONSOLIDATION|USD|266.67|1046500003|GOAL00000003|TRAN00000101|WALLETPOOLUSD|WALLETPOOLUSD1046500003|ALPACASECUUSD||0d5712ac-48ab-42fe-974a-506440f70540|1|POSTED|ALPACASECU|


		 Goal Transaction

|goal_transaction_id|transaction_type|transaction_date|transaction_amt|investment_account_id|customer_id|goal_id|status|broker_id|broker_remittance_id|transaction_sub_type|consolidation_amt|conversion_amt|order_amt|transaction_currency_id|conversion_currency_id|consolidation_currency_id|order_currency_id|transfer_amt|transfer_currency_id|remittance_amt|remittance_currency_id|distribution_amt|distribution_currency_id|transaction_sar_amount|transaction_usd_amount|
|-------------------|----------------|----------------|---------------|---------------------|-----------|-------|------|---------|--------------------|--------------------|-----------------|--------------|---------|-----------------------|----------------------|-------------------------|-----------------|------------|--------------------|--------------|----------------------|----------------|------------------------|----------------------|----------------------|
|TRAN00000101|SUBSCRIPTION|2023-12-16 06:44:55.000|1000|ALPACASECU1046500003|1046500003|GOAL00000003|CONSOLIDATION_DONE|ALPACASECU|||266.67|0|0|SAR|USD|USD||0||0||0||1000|266.67|


		 Bank Account

|bank_account_id|bank_account_num|bank_account_iban|bank_account_name|bank_id|bank_account_type|currency_id|balance_amt|available_amt|bank_balance_amt|broker_id|payment_channel_id|wallet_pool_id|status|bank_statement_offset|
|---------------|----------------|-----------------|-----------------|-------|-----------------|-----------|-----------|-------------|----------------|---------|------------------|--------------|------|---------------------|
|WALLETPOOLSAR|0108065554100010|SA9230400108065554100010||ARNBSARI|WALLET_POOL|SAR|2090|2090|3090|ALPACASECU||WALLETPOOLSAR|ACTIVE||
|WALLETPOOLUSD|0108052004590026|SA2730400108052004590026||ARNBSARI|WALLET_POOL|USD|8996.55|8996.55|8996.55|ALPACASECU||WALLETPOOLUSD|ACTIVE||
|ALPACASECUUSD|0108020000010015|SA5330400108020000010015||ARNBSARI|BROKER|USD|266.67|266.67|0|ALPACASECU|||ACTIVE||


		 Bank Sub Account

|bank_sub_account_id|bank_account_num|bank_account_iban|bank_account_name|bank_id|bank_account_id|currency_id|balance_amt|available_amt|customer_id|status|wallet_pool_id|bank_statement_offset|bank_balance_amt|
|-------------------|----------------|-----------------|-----------------|-------|---------------|-----------|-----------|-------------|-----------|------|--------------|---------------------|----------------|
|WALLETPOOLSAR1046500003|0108055667680369|SA1130400108055667680369|Sulaiman|ARNBSARI|WALLETPOOLSAR|SAR|2090|2090|1046500003|ACTIVE|WALLETPOOLSAR||3090|
|WALLETPOOLUSD1046500003|0108095164500016|SA1830400108095164500016|Sulaiman|ARNBSARI|WALLETPOOLUSD|USD|8793.55|8793.55|1046500003|ACTIVE|WALLETPOOLUSD||8793.55|


		 Bank Entry

|entry_id|bank_account_id|bank_sub_account_id|posting_date|posting_desc|posting_type|currency_id|posting_amt|goal_transaction_id|bank_journal_id|broker_remittance_id|bank_ref|bank_running_balance_amt|status|goal_id|is_bank_statement_matched|goal_transaction_type|is_remittance_matched|wallet_pool_id|wallet_payment_id|
|--------|---------------|-------------------|------------|------------|------------|-----------|-----------|-------------------|---------------|--------------------|--------|------------------------|------|-------|-------------------------|---------------------|---------------------|--------------|-----------------|
|BACE00000343|WALLETPOOLUSD|WALLETPOOLUSD1046500003|2023-12-18 10:53:25.000||WITHDRAWAL|USD|266.67|TRAN00000101|800100000481||||POSTED|||SUBSCRIPTION||||
|BACE00000344|ALPACASECUUSD||2023-12-18 10:53:26.000||DEPOSIT|USD|266.67|TRAN00000101|800100000481||||POSTED|||SUBSCRIPTION||||


		 Goal

|goal_id|customer_id|goal_name|goal_name_ar|target_sar_amt|start_date|end_date|duration_months|balance_sar_amt|interim_usd_amt|recurring_sar_amt|recurring_next_date|portfolio_id|status|risk_level|initial_sar_amt|investment_balance_amt|investment_available_amt|transit_usd_amt|investment_account_id|broker_id|investment_currency_id|expected_roi_sar_amt|portfolio_changed_date|
|-------|-----------|---------|------------|--------------|----------|--------|---------------|---------------|---------------|-----------------|-------------------|------------|------|----------|---------------|----------------------|------------------------|---------------|---------------------|---------|----------------------|--------------------|----------------------|
|GOAL00000003|1046500003|New Car||0|2023-01-01 05:30:00.000|2024-12-30 05:30:00.000|0|0|0|0|2024-06-30 05:30:00.000|25acf30f-99b0-4745-8d54-27751904216a|ACTIVE||0|0|0|266.67||||||


-------------------------------------------------------------------------------

### Subscription Remittance

#### Initiate

		 Goal Transaction

|goal_transaction_id|transaction_type|transaction_date|transaction_amt|investment_account_id|customer_id|goal_id|status|broker_id|broker_remittance_id|transaction_sub_type|consolidation_amt|conversion_amt|order_amt|transaction_currency_id|conversion_currency_id|consolidation_currency_id|order_currency_id|transfer_amt|transfer_currency_id|remittance_amt|remittance_currency_id|distribution_amt|distribution_currency_id|transaction_sar_amount|transaction_usd_amount|
|-------------------|----------------|----------------|---------------|---------------------|-----------|-------|------|---------|--------------------|--------------------|-----------------|--------------|---------|-----------------------|----------------------|-------------------------|-----------------|------------|--------------------|--------------|----------------------|----------------|------------------------|----------------------|----------------------|
|TRAN00000101|SUBSCRIPTION|2023-12-16 06:44:55.000|1000|ALPACASECU1046500003|1046500003|GOAL00000003|REMITTANCE_INITIATED|ALPACASECU|900100000341||266.67|0|0|SAR|USD|USD||0||0||0||1000|266.67|

		 Bank Account

|bank_account_id|bank_account_num|bank_account_iban|bank_account_name|bank_id|bank_account_type|currency_id|balance_amt|available_amt|bank_balance_amt|broker_id|payment_channel_id|wallet_pool_id|status|bank_statement_offset|
|---------------|----------------|-----------------|-----------------|-------|-----------------|-----------|-----------|-------------|----------------|---------|------------------|--------------|------|---------------------|
|WALLETPOOLSAR|0108065554100010|SA9230400108065554100010||ARNBSARI|WALLET_POOL|SAR|2090|2090|3090|ALPACASECU||WALLETPOOLSAR|ACTIVE||
|WALLETPOOLUSD|0108052004590026|SA2730400108052004590026||ARNBSARI|WALLET_POOL|USD|8996.55|8996.55|8996.55|ALPACASECU||WALLETPOOLUSD|ACTIVE||
|ALPACASECUUSD|0108020000010015|SA5330400108020000010015||ARNBSARI|BROKER|USD|266.67|0|38684.89|ALPACASECU|||ACTIVE||

		 Broker

|broker_id|broker_name|broker_name_ar|currency_id|broker_abbr|current_account_num|current_account_bank_id|current_account_currency_id|current_account_name|current_account_iban|outward_created_amt|outward_requested_amt|outward_transit_amt|outward_remitted_amt|inward_created_amt|inward_requested_amt|inward_transit_amt|inward_remitted_amt|address_line_1|address_line_2|address_line_3|
|---------|-----------|--------------|-----------|-----------|-------------------|-----------------------|---------------------------|--------------------|--------------------|-------------------|---------------------|-------------------|--------------------|------------------|--------------------|------------------|-------------------|--------------|--------------|--------------|
|ALPACASECU|Alpaca Securities LLC|Alpaca Securities LLC|USD|ALP|0108020000990010|HATRUS44|EUR|Alpaca Securities LLC|49033073-6233-4d14-aec2-a5e1f40861e5|266.67|0|0|0|0|0|0|0|abcdf;rf|Suite 456 45|Building md|

		 Broker Remittance

|broker_remittance_id|broker_id|remittance_date|remittance_type|remittance_currency_id|remittance_amt|broker_ref|retry_ct|status|bank_ref|
|--------------------|---------|---------------|---------------|----------------------|--------------|----------|--------|------|--------|
|900100000341|ALPACASECU|2023-12-18 11:12:49.000|OUTWARD|USD|266.67||0|CREATED||

		 Investment Account

|investment_account_id|broker_id|is_firm_account|account_currency_id|balance_amt|available_amt|customer_id|status|investment_account_ref|investment_account_num|broker_statement_offset|broker_balance_amt|
|---------------------|---------|---------------|-------------------|-----------|-------------|-----------|------|----------------------|----------------------|-----------------------|------------------|
|ALPACASECUAKASIAFIRM|ALPACASECU|yes|USD|50633.34|50366.67|AKASIAFIRM|ACTIVE|aa98cfeb-6f82-3fe1-8e6e-56c909b7d984|3497547SW||50366.67|

#### Request

		 Broker Remittance

|broker_remittance_id|broker_id|remittance_date|remittance_type|remittance_currency_id|remittance_amt|broker_ref|retry_ct|status|bank_ref|
|--------------------|---------|---------------|---------------|----------------------|--------------|----------|--------|------|--------|
|900100000341|ALPACASECU|2023-12-18 11:12:49.000|OUTWARD|USD|266.67||1|REQUESTED|c19399aa-3f53-4097-bc45-a35c17c1ba1a|

		 Broker

|broker_id|broker_name|broker_name_ar|currency_id|broker_abbr|current_account_num|current_account_bank_id|current_account_currency_id|current_account_name|current_account_iban|outward_created_amt|outward_requested_amt|outward_transit_amt|outward_remitted_amt|inward_created_amt|inward_requested_amt|inward_transit_amt|inward_remitted_amt|address_line_1|address_line_2|address_line_3|
|---------|-----------|--------------|-----------|-----------|-------------------|-----------------------|---------------------------|--------------------|--------------------|-------------------|---------------------|-------------------|--------------------|------------------|--------------------|------------------|-------------------|--------------|--------------|--------------|
|ALPACASECU|Alpaca Securities LLC|Alpaca Securities LLC|USD|ALP|0108020000990010|HATRUS44|EUR|Alpaca Securities LLC|49033073-6233-4d14-aec2-a5e1f40861e5|0|266.67|0|0|0|0|0|0|abcdf;rf|Suite 456 45|Building md|

#### Status

		 Broker Remittance

|broker_remittance_id|broker_id|remittance_date|remittance_type|remittance_currency_id|remittance_amt|broker_ref|retry_ct|status|bank_ref|
|--------------------|---------|---------------|---------------|----------------------|--------------|----------|--------|------|--------|
|900100000341|ALPACASECU|2023-12-18 11:12:49.000|OUTWARD|USD|266.67||1|TRANSIT|c19399aa-3f53-4097-bc45-a35c17c1ba1a|

		 Broker

|broker_id|broker_name|broker_name_ar|currency_id|broker_abbr|current_account_num|current_account_bank_id|current_account_currency_id|current_account_name|current_account_iban|outward_created_amt|outward_requested_amt|outward_transit_amt|outward_remitted_amt|inward_created_amt|inward_requested_amt|inward_transit_amt|inward_remitted_amt|address_line_1|address_line_2|address_line_3|
|---------|-----------|--------------|-----------|-----------|-------------------|-----------------------|---------------------------|--------------------|--------------------|-------------------|---------------------|-------------------|--------------------|------------------|--------------------|------------------|-------------------|--------------|--------------|--------------|
|ALPACASECU|Alpaca Securities LLC|Alpaca Securities LLC|USD|ALP|0108020000990010|HATRUS44|EUR|Alpaca Securities LLC|49033073-6233-4d14-aec2-a5e1f40861e5|0|0|266.67|0|0|0|0|0|abcdf;rf|Suite 456 45|Building md|

		 Bank Account

|bank_account_id|bank_account_num|bank_account_iban|bank_account_name|bank_id|bank_account_type|currency_id|balance_amt|available_amt|bank_balance_amt|broker_id|payment_channel_id|wallet_pool_id|status|bank_statement_offset|
|---------------|----------------|-----------------|-----------------|-------|-----------------|-----------|-----------|-------------|----------------|---------|------------------|--------------|------|---------------------|
|ALPACASECUUSD|0108020000010015|SA5330400108020000010015||ARNBSARI|BROKER|USD|0|0|38684.89|ALPACASECU|||ACTIVE||

		 Bank Entry

|entry_id|bank_account_id|bank_sub_account_id|posting_date|posting_desc|posting_type|currency_id|posting_amt|goal_transaction_id|bank_journal_id|broker_remittance_id|bank_ref|bank_running_balance_amt|status|goal_id|is_bank_statement_matched|goal_transaction_type|is_remittance_matched|wallet_pool_id|wallet_payment_id|
|--------|---------------|-------------------|------------|------------|------------|-----------|-----------|-------------------|---------------|--------------------|--------|------------------------|------|-------|-------------------------|---------------------|---------------------|--------------|-----------------|
|BACE00000344|ALPACASECUUSD||2023-12-18 10:53:26.000||DEPOSIT|USD|266.67|TRAN00000101|800100000481||||POSTED|||SUBSCRIPTION||||
|BACE00000345|ALPACASECUUSD||2023-12-18 11:40:48.000||WITHDRAWAL|USD|266.67|||900100000341|||POSTED|||SUBSCRIPTION||||


#### Broker Request

		 Broker Remittance

|broker_remittance_id|broker_id|remittance_date|remittance_type|remittance_currency_id|remittance_amt|broker_ref|retry_ct|status|bank_ref|
|--------------------|---------|---------------|---------------|----------------------|--------------|----------|--------|------|--------|
|900100000341|ALPACASECU|2023-12-18 11:12:49.000|OUTWARD|USD|266.67|7bcf5eab-e994-4f14-9cb7-95e07cde3c01|1|PENDING|c19399aa-3f53-4097-bc45-a35c17c1ba1a|

#### Broker Status

		 Broker Remittance

|broker_remittance_id|broker_id|remittance_date|remittance_type|remittance_currency_id|remittance_amt|broker_ref|retry_ct|status|bank_ref|
|--------------------|---------|---------------|---------------|----------------------|--------------|----------|--------|------|--------|
|900100000341|ALPACASECU|2023-12-18 11:12:49.000|OUTWARD|USD|266.67|7bcf5eab-e994-4f14-9cb7-95e07cde3c01|1|REMITTED|c19399aa-3f53-4097-bc45-a35c17c1ba1a|


		 Investment Account

|investment_account_id|broker_id|is_firm_account|account_currency_id|balance_amt|available_amt|customer_id|status|investment_account_ref|investment_account_num|broker_statement_offset|broker_balance_amt|
|---------------------|---------|---------------|-------------------|-----------|-------------|-----------|------|----------------------|----------------------|-----------------------|------------------|
|ALPACASECUAKASIAFIRM|ALPACASECU|yes|USD|50633.34|50633.34|AKASIAFIRM|ACTIVE|aa98cfeb-6f82-3fe1-8e6e-56c909b7d984|3497547SW||50366.67|


		 Goal Transaction

|goal_transaction_id|transaction_type|transaction_date|transaction_amt|investment_account_id|customer_id|goal_id|status|broker_id|broker_remittance_id|transaction_sub_type|consolidation_amt|conversion_amt|order_amt|transaction_currency_id|conversion_currency_id|consolidation_currency_id|order_currency_id|transfer_amt|transfer_currency_id|remittance_amt|remittance_currency_id|distribution_amt|distribution_currency_id|transaction_sar_amount|transaction_usd_amount|
|-------------------|----------------|----------------|---------------|---------------------|-----------|-------|------|---------|--------------------|--------------------|-----------------|--------------|---------|-----------------------|----------------------|-------------------------|-----------------|------------|--------------------|--------------|----------------------|----------------|------------------------|----------------------|----------------------|
|TRAN00000101|SUBSCRIPTION|2023-12-16 06:44:55.000|1000|ALPACASECU1046500003|1046500003|GOAL00000003|REMITTANCE_DONE|ALPACASECU|900100000341||0|0|0|SAR|USD|USD||0||266.67||0||1000|266.67|


		 Broker

|broker_id|broker_name|broker_name_ar|currency_id|broker_abbr|current_account_num|current_account_bank_id|current_account_currency_id|current_account_name|current_account_iban|outward_created_amt|outward_requested_amt|outward_transit_amt|outward_remitted_amt|inward_created_amt|inward_requested_amt|inward_transit_amt|inward_remitted_amt|address_line_1|address_line_2|address_line_3|
|---------|-----------|--------------|-----------|-----------|-------------------|-----------------------|---------------------------|--------------------|--------------------|-------------------|---------------------|-------------------|--------------------|------------------|--------------------|------------------|-------------------|--------------|--------------|--------------|
|ALPACASECU|Alpaca Securities LLC|Alpaca Securities LLC|USD|ALP|0108020000990010|HATRUS44|EUR|Alpaca Securities LLC|49033073-6233-4d14-aec2-a5e1f40861e5|0|0|0|266.67|0|0|0|0|abcdf;rf|Suite 456 45|Building md|


		 Alpaca Dashboard


![[Pasted image 20231218122135.png]]


![[Pasted image 20231218122306.png]]

-------------------------------------------------------------------------------
### Subscription Transfer

#### Initiate

		Investment Cash Journal

|journal_id|journal_date|journal_type|journal_currency_id|journal_amt|goal_id|goal_transaction_id|from_investment_account_id|to_investment_account_id|broker_ref|status|from_customer_id|to_customer_id|broker_id|
|----------|------------|------------|-------------------|-----------|-------|-------------------|--------------------------|------------------------|----------|------|----------------|--------------|---------|
|INCJ00000121|2023-12-18 13:12:16.000|SUBSCRIPTION_DISTRIBUTION|USD|266.67|GOAL00000003|TRAN00000101|ALPACASECUAKASIAFIRM|ALPACASECU1046500003||CREATED|AKASIAFIRM|1046500003||

		 Goal Transaction

|goal_transaction_id|transaction_type|transaction_date|transaction_amt|investment_account_id|customer_id|goal_id|status|broker_id|broker_remittance_id|transaction_sub_type|consolidation_amt|conversion_amt|order_amt|transaction_currency_id|conversion_currency_id|consolidation_currency_id|order_currency_id|transfer_amt|transfer_currency_id|remittance_amt|remittance_currency_id|distribution_amt|distribution_currency_id|transaction_sar_amount|transaction_usd_amount|
|-------------------|----------------|----------------|---------------|---------------------|-----------|-------|------|---------|--------------------|--------------------|-----------------|--------------|---------|-----------------------|----------------------|-------------------------|-----------------|------------|--------------------|--------------|----------------------|----------------|------------------------|----------------------|----------------------|
|TRAN00000101|SUBSCRIPTION|2023-12-16 06:44:55.000|1000|ALPACASECU1046500003|1046500003|GOAL00000003|TRANSFER_INITIATED|ALPACASECU|900100000341||0|0|0|SAR|USD|USD||0||266.67||0||1000|266.67|

		 Goal

|goal_id|customer_id|goal_name|goal_name_ar|target_sar_amt|start_date|end_date|duration_months|balance_sar_amt|interim_usd_amt|recurring_sar_amt|recurring_next_date|portfolio_id|status|risk_level|initial_sar_amt|investment_balance_amt|investment_available_amt|transit_usd_amt|investment_account_id|broker_id|investment_currency_id|expected_roi_sar_amt|portfolio_changed_date|
|-------|-----------|---------|------------|--------------|----------|--------|---------------|---------------|---------------|-----------------|-------------------|------------|------|----------|---------------|----------------------|------------------------|---------------|---------------------|---------|----------------------|--------------------|----------------------|
|GOAL00000003|1046500003|New Car||0|2023-01-01 05:30:00.000|2024-12-30 05:30:00.000|0|0|0|0|2024-06-30 05:30:00.000|25acf30f-99b0-4745-8d54-27751904216a|ACTIVE||0|266.67|0|0||||||

		 Investment Account

|investment_account_id|broker_id|is_firm_account|account_currency_id|balance_amt|available_amt|customer_id|status|investment_account_ref|investment_account_num|broker_statement_offset|broker_balance_amt|
|---------------------|---------|---------------|-------------------|-----------|-------------|-----------|------|----------------------|----------------------|-----------------------|------------------|
|ALPACASECUAKASIAFIRM|ALPACASECU|yes|USD|50633.34|50366.67|AKASIAFIRM|ACTIVE|aa98cfeb-6f82-3fe1-8e6e-56c909b7d984|3497547SW||50366.67|
|ALPACASECU1046500003|ALPACASECU|no|USD|529.27|262.6|1046500003|ACTIVE|5524f986-4a70-4d06-9864-4d6700c4dd6e|351383055||262.6|


#### Request

		 Investment Cash Journal

|journal_id|journal_date|journal_type|journal_currency_id|journal_amt|goal_id|goal_transaction_id|from_investment_account_id|to_investment_account_id|broker_ref|status|from_customer_id|to_customer_id|broker_id|
|----------|------------|------------|-------------------|-----------|-------|-------------------|--------------------------|------------------------|----------|------|----------------|--------------|---------|
|INCJ00000121|2023-12-18 13:12:16.000|SUBSCRIPTION_DISTRIBUTION|USD|266.67|GOAL00000003|TRAN00000101|ALPACASECUAKASIAFIRM|ALPACASECU1046500003|d824d095-4ad6-4e94-8d45-eba5aa0a62b6|REQUESTED|AKASIAFIRM|1046500003||

#### Status

		 Goal Transaction

|goal_transaction_id|transaction_type|transaction_date|transaction_amt|investment_account_id|customer_id|goal_id|status|broker_id|broker_remittance_id|transaction_sub_type|consolidation_amt|conversion_amt|order_amt|transaction_currency_id|conversion_currency_id|consolidation_currency_id|order_currency_id|transfer_amt|transfer_currency_id|remittance_amt|remittance_currency_id|distribution_amt|distribution_currency_id|transaction_sar_amount|transaction_usd_amount|
|-------------------|----------------|----------------|---------------|---------------------|-----------|-------|------|---------|--------------------|--------------------|-----------------|--------------|---------|-----------------------|----------------------|-------------------------|-----------------|------------|--------------------|--------------|----------------------|----------------|------------------------|----------------------|----------------------|
|TRAN00000101|SUBSCRIPTION|2023-12-16 06:44:55.000|1000|ALPACASECU1046500003|1046500003|GOAL00000003|TRANSFER_DONE|ALPACASECU|900100000341||0|0|0|SAR|USD|USD||266.67||0||0||1000|266.67|

		 Goal

|goal_id|customer_id|goal_name|goal_name_ar|target_sar_amt|start_date|end_date|duration_months|balance_sar_amt|interim_usd_amt|recurring_sar_amt|recurring_next_date|portfolio_id|status|risk_level|initial_sar_amt|investment_balance_amt|investment_available_amt|transit_usd_amt|investment_account_id|broker_id|investment_currency_id|expected_roi_sar_amt|portfolio_changed_date|
|-------|-----------|---------|------------|--------------|----------|--------|---------------|---------------|---------------|-----------------|-------------------|------------|------|----------|---------------|----------------------|------------------------|---------------|---------------------|---------|----------------------|--------------------|----------------------|
|GOAL00000003|1046500003|New Car||0|2023-01-01 05:30:00.000|2024-12-30 05:30:00.000|0|0|0|0|2024-06-30 05:30:00.000|25acf30f-99b0-4745-8d54-27751904216a|ACTIVE||0|266.67|266.67|0||||||


		 Investment Account

|investment_account_id|broker_id|is_firm_account|account_currency_id|balance_amt|available_amt|customer_id|status|investment_account_ref|investment_account_num|broker_statement_offset|broker_balance_amt|
|---------------------|---------|---------------|-------------------|-----------|-------------|-----------|------|----------------------|----------------------|-----------------------|------------------|
|ALPACASECUAKASIAFIRM|ALPACASECU|yes|USD|50366.67|50366.67|AKASIAFIRM|ACTIVE|aa98cfeb-6f82-3fe1-8e6e-56c909b7d984|3497547SW||50366.67|
|ALPACASECU1046500003|ALPACASECU|no|USD|529.27|529.27|1046500003|ACTIVE|5524f986-4a70-4d06-9864-4d6700c4dd6e|351383055||262.6|


		 Investment Cash Entry

|entry_id|investment_account_id|posting_date|posting_desc|posting_type|currency_id|posting_amt|customer_id|goal_id|goal_transaction_id|cash_journal_id|status|goal_transaction_type|is_cash_matched|order_id|broker_remittance_id|activity_type|
|--------|---------------------|------------|------------|------------|-----------|-----------|-----------|-------|-------------------|---------------|------|---------------------|---------------|--------|--------------------|-------------|
|INCE00000202|ALPACASECUAKASIAFIRM|2023-12-18 00:00:00.000||WITHDRAWAL|USD|266.67|AKASIAFIRM|GOAL00000003|TRAN00000101|INCJ00000121|POSTED|SUBSCRIPTION|||||
|INCE00000203|ALPACASECU1046500003|2023-12-18 00:00:00.000||DEPOSIT|USD|266.67|AKASIAFIRM|GOAL00000003|TRAN00000101|INCJ00000121|POSTED|SUBSCRIPTION|||||



		 Investment Cash Journal

|journal_id|journal_date|journal_type|journal_currency_id|journal_amt|goal_id|goal_transaction_id|from_investment_account_id|to_investment_account_id|broker_ref|status|from_customer_id|to_customer_id|broker_id|
|----------|------------|------------|-------------------|-----------|-------|-------------------|--------------------------|------------------------|----------|------|----------------|--------------|---------|
|INCJ00000121|2023-12-18 13:12:16.000|SUBSCRIPTION_DISTRIBUTION|USD|266.67|GOAL00000003|TRAN00000101|ALPACASECUAKASIAFIRM|ALPACASECU1046500003|d824d095-4ad6-4e94-8d45-eba5aa0a62b6|POSTED|AKASIAFIRM|1046500003||


![[Pasted image 20231218153549.png]]

------------------------------------------------------------------------------------

### Subscription Buy Order

#### Initiate

		 Goal Transaction

|goal_transaction_id|transaction_type|transaction_date|transaction_amt|investment_account_id|customer_id|goal_id|status|broker_id|broker_remittance_id|transaction_sub_type|consolidation_amt|conversion_amt|order_amt|transaction_currency_id|conversion_currency_id|consolidation_currency_id|order_currency_id|transfer_amt|transfer_currency_id|remittance_amt|remittance_currency_id|distribution_amt|distribution_currency_id|transaction_sar_amount|transaction_usd_amount|
|-------------------|----------------|----------------|---------------|---------------------|-----------|-------|------|---------|--------------------|--------------------|-----------------|--------------|---------|-----------------------|----------------------|-------------------------|-----------------|------------|--------------------|--------------|----------------------|----------------|------------------------|----------------------|----------------------|
|TRAN00000101|SUBSCRIPTION|2023-12-16 06:44:55.000|1000|ALPACASECU1046500003|1046500003|GOAL00000003|ORDER_INITIATED|ALPACASECU|900100000341||0|0|0|SAR|USD|USD||266.67||0||0||1000|266.67|

		 Goal

|goal_id|customer_id|goal_name|goal_name_ar|target_sar_amt|start_date|end_date|duration_months|balance_sar_amt|interim_usd_amt|recurring_sar_amt|recurring_next_date|portfolio_id|status|risk_level|initial_sar_amt|investment_balance_amt|investment_available_amt|transit_usd_amt|investment_account_id|broker_id|investment_currency_id|expected_roi_sar_amt|portfolio_changed_date|
|-------|-----------|---------|------------|--------------|----------|--------|---------------|---------------|---------------|-----------------|-------------------|------------|------|----------|---------------|----------------------|------------------------|---------------|---------------------|---------|----------------------|--------------------|----------------------|
|GOAL00000003|1046500003|New Car||0|2023-01-01 05:30:00.000|2024-12-30 05:30:00.000|0|0|0|0|2024-06-30 05:30:00.000|25acf30f-99b0-4745-8d54-27751904216a|ACTIVE||0|266.67|0|0||||||

		 Investment Account

|investment_account_id|broker_id|is_firm_account|account_currency_id|balance_amt|available_amt|customer_id|status|investment_account_ref|investment_account_num|broker_statement_offset|broker_balance_amt|
|---------------------|---------|---------------|-------------------|-----------|-------------|-----------|------|----------------------|----------------------|-----------------------|------------------|
|ALPACASECUAKASIAFIRM|ALPACASECU|yes|USD|50366.67|50366.67|AKASIAFIRM|ACTIVE|aa98cfeb-6f82-3fe1-8e6e-56c909b7d984|3497547SW||50366.67|
|ALPACASECU1046500003|ALPACASECU|no|USD|529.27|262.6|1046500003|ACTIVE|5524f986-4a70-4d06-9864-4d6700c4dd6e|351383055||262.6|

		 Order

|order_id|security_id|order_type|order_context|order_date|order_currency_id|order_amt|investment_account_id|customer_id|goal_id|goal_transaction_id|broker_id|broker_ref|status|order_qty|filled_date|settled_date|
|--------|-----------|----------|-------------|----------|-----------------|---------|---------------------|-----------|-------|-------------------|---------|----------|------|---------|-----------|------------|
|ORDR00000121|BBSC|BUY|SUBSCRIPTION|2023-12-18 16:02:19.000|USD|53.334|ALPACASECU1046500003|1046500003|GOAL00000003|TRAN00000101|ALPACASECU||CREATED|0|||
|ORDR00000122|CHIE|BUY|SUBSCRIPTION|2023-12-18 16:02:20.000|USD|80.001|ALPACASECU1046500003|1046500003|GOAL00000003|TRAN00000101|ALPACASECU||CREATED|0|||
|ORDR00000123|CUT|BUY|SUBSCRIPTION|2023-12-18 16:02:20.000|USD|133.335|ALPACASECU1046500003|1046500003|GOAL00000003|TRAN00000101|ALPACASECU||CREATED|0|||


#### Request


		 Orders

|order_id|security_id|order_type|order_context|order_date|order_currency_id|order_amt|investment_account_id|customer_id|goal_id|goal_transaction_id|broker_id|broker_ref|status|order_qty|filled_date|settled_date|
|--------|-----------|----------|-------------|----------|-----------------|---------|---------------------|-----------|-------|-------------------|---------|----------|------|---------|-----------|------------|
|ORDR00000121|BBSC|BUY|SUBSCRIPTION|2023-12-18 16:02:19.000|USD|53.334|ALPACASECU1046500003|1046500003|GOAL00000003|TRAN00000101|ALPACASECU|896850b8-4624-49e3-8eab-20242b2b6a58|REQUESTED|0|||
|ORDR00000122|CHIE|BUY|SUBSCRIPTION|2023-12-18 16:02:20.000|USD|80.001|ALPACASECU1046500003|1046500003|GOAL00000003|TRAN00000101|ALPACASECU|2c9559c4-97c1-4668-969e-159d7b26dc6c|REQUESTED|0|||
|ORDR00000123|CUT|BUY|SUBSCRIPTION|2023-12-18 16:02:20.000|USD|133.335|ALPACASECU1046500003|1046500003|GOAL00000003|TRAN00000101|ALPACASECU|f5e6fad6-9791-4f2c-8e63-62abed523844|REQUESTED|0|||


#### Status

