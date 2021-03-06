# lita-reddit

A plugin that allows for watching the /new queue of a subreddit and posting new items to a chat room.

## Installation

Add lita-reddit to your Lita instance's Gemfile:

``` ruby
gem "lita-reddit"
```

## Configuration

``` ruby
# The client ID from the Reddit API
config.handlers.reddit.client_id = "client_from_api"
# The secret ID from the Reddit API
config.handlers.reddit.client_secret = "secret_from_api"
# List of subreddit/channel to update pairs
config.handlers.reddit.reddits = [{subreddit: "subreddit_name", channel: "##channel_to_update"}]
# The delay to wait before starting the polling in seconds (optional, defaults to 30s)
config.handlers.reddit.startup_delay = 30
# The interval in between requests (optional, defaults to 300s)
config.handlers.reddit.poll_interval = 300
# The limit of number of posts to output from any sub per poll (optional, defaults to 3)
config.handlers.reddit.post_limit = 3
# The string to use when posting to the channel. Supports %{user}, %{title}, %{subreddit}, %{id},
# and ${shortlink}. (Optional, defaults to "/u/%{user}: %{title} | /r/%{subreddit} | %{shortlink}")
config.handlers.reddit.post_text = "/u/%{user}: %{title} | /r/%{subreddit} | %{shortlink}"
```

## Usage

Add a collection of subreddit and channel pairs to the reddits array, create a script api key on reddit and enter those values, and then restart lita

## License

[MIT](http://opensource.org/licenses/MIT)
