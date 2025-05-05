# @jaspermayone/ruby-rails-template

## Setup Guide

### Initial Setup

After cloning this repository, follow these steps to configure your application:

1. Generate unique credentials:

   ```bash
   bin/regenerate-credentials
   ```

   This creates a secure master key and credentials file specific to your project.

2. Generate a Lockbox encryption key by running in the Rails console:

   ```ruby
   Lockbox.generate_key
   ```
   
3. Generate an ARE Key by running
    ```bash
    bin/rails db:encryption:init
    ```

4. Add the generated keys to your credentials:

   ```bash
   rails credentials:edit
   ```

   Then insert the keys in this format (replace the replaceme's with generated creds):

   ```yaml

    active_record_encryption:
      primary_key: REPLACEME
      deterministic_key: REPLACEME
      key_derivation_salt: REPLACEME

   lockbox:
     master_key: REPLACEME
   ```

5. Replace all instances of "REPLACEMEWITHAPPNAME" with your actual application name.

6. Install dependencies:

   ```bash
   bundle install
   ```

### Next Steps

You're ready to start development! Consider reviewing the following:

- Database configuration in `config/database.yml`
- Environment variables in `.env.example` (copy to `.env` for local development)
- Test suite setup with `rails test`

## Additional Resources

- [Lockbox Documentation](https://github.com/ankane/lockbox)
- [Rails Credentials Guide](https://guides.rubyonrails.org/security.html#custom-credentials)
