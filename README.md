# DisposableMail
[![Build Status](https://travis-ci.org/oesgalha/disposable_mail.svg)](https://travis-ci.org/oesgalha/disposable_mail)
[![Code Climate](https://codeclimate.com/github/oesgalha/disposable_mail/badges/gpa.svg)](https://codeclimate.com/github/oesgalha/disposable_mail)

DisposableMail serves you a blacklist with domains from (https://en.wikipedia.org/wiki/Disposable_email_address)[disposable mail services], like `mailinator.com` or `guerrillamail`. The list can be used to prevent sending mails to these domains (which probably won't be open), or to prevent dummy users registration in your website.

The domain list comes from this git repo:
https://github.com/martenson/disposable-email-domains

And this gem syncs with it through a git submodule (see the data folder).

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'disposable_mail', github: 'oesgalha/disposable_mail'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install disposable_mail

## Usage

```ruby
DisposableMail.list # => ["0815.ru", "0815.su", "0clickemail.com", "0-mail.com", "0wnd.net", "0wnd.org", "10minut.com.pl", ... ]

DisposableMail.include? "dummy@mailinator.com" # => true

DisposableMail.include? "bot@guerillamail.com" # => true

DisposableMail.include? "legit-person@yahoo.com" # => false
```

## Contributing

1. Fork it ( https://github.com/oesgalha/disposable_mail/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
