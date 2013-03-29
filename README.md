# Aggcat

  Intuit Customer Account Data API client

## Installation

Aggcat is available through [Rubygems](http://rubygems.org/gems/aggcat) and can be installed via:

```
$ gem install aggcat
```

or add it to your Gemfile like this:

```
gem 'aggcat'
```

## Usage

```ruby
require 'aggcat'

# Aggcat global configuration
Aggcat.configure do |config|
  config.issuer_id = YOUR_ISSUER_ID
  config.consumer_key = YOUR_CONSUMER_KEY
  config.consumer_secret = YOUR_CONSUMER_SECRET
  config.certificate_path = '/path/to/your/certificate/key'
end

# alternatively, specify configuration options when instantiating an Aggcat::Client
client = Aggcat::Client.new(
  issuer_id: YOUR_ISSUER_ID,
  consumer_key: YOUR_CONSUMER_KEY,
  consumer_secret: YOUR_CONSUMER_SECRET,
  certificate_path: '/path/to/your/certificate/key'
)

# get all supported financial institutions
Aggcat.institutions

# get details for Bank of America
Aggcat.institution(14007)

# add new financial account to aggregate from Bank of America
Aggcat.discover_and_add_accounts(14007, username, password)

# get already aggregated financial account
Aggcat.account(account_id)

# get all aggregated accounts
Aggcat.accounts

# delete account
Aggcat.delete_account(account_id)

# get account transactions
Aggcat.account_transactions(account_id, start_date, end_date)

# delete all aggregated customers
Aggcat.delete_customers

```

## Documentation

Please make sure to read Intuit's [Account Data API](http://docs.developer.intuit.com/0020_Aggregation_Categorization_Apps/AggCat_API/0020_API_Documentation) docs.

## Copyright
Copyright (c) 2013 Gene Drabkin.
See [LICENSE][] for details.

[license]: LICENSE.md
