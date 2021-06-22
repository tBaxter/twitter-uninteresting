# twitter-uninteresting
A little snippet to run in the web inspector and turn off Twitter interests.


All credit goes to Stephen Parker, who wrote this up [back in February](https://www.neowin.net/news/turn-off-topic-suggestions-and-interests-at-twitter-with-this-handy-script/). I just copied it here so I would be able to find it again.

# How to do this
1. Go to your twitter interests page: https://twitter.com/settings/your_twitter_data/twitter_interests
2. You'll see a bunch of stuff checked. Twitter intentionally makes it very difficult for you to control this page in any meaningful way. 
3. Open a web inspector. 
4. Run the script below:

```
var timer=1000; document.querySelectorAll( "div > input[type='checkbox']:checked" ).forEach((interest) => { setTimeout( function(){interest.click(); interest.scrollIntoView()},timer ); timer+=2000; });
```

You can change the timer values to something faster, but Twitter will throw more "over capacity" errors. They really don't want you controlling your own interests.
