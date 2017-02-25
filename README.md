# Pushjs
[![Gem Version](https://badge.fury.io/rb/pushjs.svg)](https://badge.fury.io/rb/pushjs)

This gem provides the push.js Javascript library for your Rails application.

pushjs gem is the integration of push.js javascript library for your Rails applications.

push.js cross-browser solution for the JavaScript Notifications API
source: https://github.com/Nickersoft/push.js

Ruby gems url: https://rubygems.org/gems/pushjs

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'pushjs'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install pushjs

Now you need to edit your `app/assets/javascripts/application.js` file and add the following line:
``` javascript
//= require push
```

## Usage

Here is the example working code to test with your Rails application.

Add this sample code to your `app/assets/javascripts/application.js` file


#### Creating Notifications ####

```javascript
Push.create('Hello World!')
```

#### Closing Notifications ####
When it comes to closing notifications, you have a few options. You can either set a timeout (see "Options"), call
Push's close() method, or pass around the notification's promise object and then call close() directly. Push's close()
method will only work with newer browsers, taking in a notification's unique tag name and closing the first notification
it finds with that tag:

```javascript
Push.create('Hello World!', {
    tag: 'foo'
});

// Somewhere later in your code...

Push.close('foo');
```



### Options ###

The only required argument in a Push call is a title. However, that doesn't mean you can't add a little something extra.
You can pass in options to Push as well, like so:

```javascript
Push.create('Hello World!', {
    body: 'This is some body content!',
    icon: {
        x16: 'images/icon-x16.png',
        x32: 'images/icon-x32.png'
    },
    timeout: 5000
});
```

## Full documentation 

Read the clipboard.js documentation here https://github.com/Nickersoft/push.js for full usage information.


## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing
Bug reports and pull requests are welcome on GitHub at https://github.com/zainalmustofa/pushjs. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

1. Fork it ( https://github.com/zainalmustofa/pushjs/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

