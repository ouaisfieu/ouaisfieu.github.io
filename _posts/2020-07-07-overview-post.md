---
layout: post
author: Abhinav Saxena
tags: [overview, moonwalk]
---

Lorem ipsum[^1] dolor sit amet, consectetur adipiscing elit. Pellentesque vel lacinia neque. Praesent nulla quam, ullamcorper in sollicitudin ac, molestie sed justo. Cras aliquam, sapien id consectetur accumsan, augue magna faucibus ex, ut ultricies turpis tortor vel ante. In at rutrum tellus.

# Sample heading 1
## Sample heading 2
### Sample heading 3
#### Sample heading 4
##### Sample heading 5
###### Sample heading 6

Mauris viverra dictum ultricies. Vestibulum quis ipsum euismod, facilisis metus sed, varius ipsum. Donec scelerisque lacus libero, eu dignissim sem venenatis at. Etiam id nisl ut lorem gravida euismod.

## Lists

Unordered:

- Fusce non velit cursus ligula mattis convallis vel at metus[^2].
- Sed pharetra tellus massa, non elementum eros vulputate non.
- Suspendisse potenti.

Ordered:

1. Quisque arcu felis, laoreet vel accumsan sit amet, fermentum at nunc.
2. Sed massa quam, auctor in eros quis, porttitor tincidunt orci.
3. Nulla convallis id sapien ornare viverra.
4. Nam a est eget ligula pellentesque posuere.

## Blockquote

The following is a blockquote:

> Suspendisse tempus dolor nec risus sodales posuere. Proin dui dui, mollis a consectetur molestie, lobortis vitae tellus.

## Thematic breaks (<hr>)

Mauris viverra dictum ultricies[^3]. Vestibulum quis ipsum euismod, facilisis metus sed, varius ipsum. Donec scelerisque lacus libero, eu dignissim sem venenatis at. Etiam id nisl ut lorem gravida euismod. **You can put some text inside the horizontal rule like so.**

---
{: data-content="hr with text"}

Mauris viverra dictum ultricies. Vestibulum quis ipsum euismod, facilisis metus sed, varius ipsum. Donec scelerisque lacus libero, eu dignissim sem venenatis at. Etiam id nisl ut lorem gravida euismod. **Or you can just have an clean horizontal rule.**

---

Mauris viverra dictum ultricies. Vestibulum quis ipsum euismod, facilisis metus sed, varius ipsum. Donec scelerisque lacus libero, eu dignissim sem venenatis at. Etiam id nisl ut lorem gravida euismod. Or you can just have an clean horizontal rule.

## Code

Now some code:

```
const ultimateTruth = 'follow middlepath';
console.log(ultimateTruth);
```

And here is some `inline code`!

## Tables

Now a table:

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

## Images

![theme logo](http://www.abhinavsaxena.com/images/abhinav.jpeg)

This is an image[^4]

# Language Test

## Python
```python
import microrequests

mr = microrequests.init()
# mr is requests' session object and you can use it in similar manner
res = mr.get("http://httpbin.org/get")
print(res.text) 
```

## Ruby
```ruby
require 'gmail'
require 'time'
require 'yaml'
require 'erb'

if ARGV.length != 2
  puts "Syntax: #{__FILE__} gmail-username gmail-password"
  exit
end

config = YAML.load_file("#{File.dirname(__FILE__)}/config.yaml")
body = ERB.new(config['body'])

gmail = Gmail.connect(ARGV[0], ARGV[1])

# variable 'name' is important given it is used in body as well
for name, email_id in config['to'] do
  puts "sending to #{email_id}"
  email = gmail.compose do
    to email_id
    from config['from']
    subject config['subject']
    body body.result(binding)
    end
  email.deliver!
end

gmail.logout
```

## Javascript
```javascript
const path = require('path');
const { merge } = require('webpack-merge');
const common = require('./webpack.common.js');

module.exports = merge(common, {
  mode: 'development',
  devtool: 'inline-source-map',
  devServer: {
    writeToDisk: true,
    contentBase: path.join(__dirname, 'dist'),
    publicPath: path.join(__dirname, 'dist'),
    compress: true,
    port: 8000,
  },
});
```

## Elixir
```elixir
defmodule MyAppWeb.BearerAuth do

  import Plug.Conn
  alias MyApp.Account

  def init(options) do
    options
  end

  def call(conn, _options) do
    case get_bearer_auth_token(conn) do
      nil ->
        conn |> unauthorized()
      :error ->
        conn |> unauthorized()
      auth_token ->
        account =
          Account.get_from_token(auth_token)
        if account do
          assign(conn, :current_account, account)
        else
          conn |> unauthorized()
        end
    end
  end

  defp get_bearer_auth_token(conn) do
    with ["Bearer " <> auth_token] <- get_req_header(conn, "authorization") do
      auth_token
    else
      _ -> :error
    end
  end

  defp unauthorized(conn) do
    conn
    |> resp(401, "Unauthorized")
    |> halt()
  end
end

```

## CSS
```css
.highlight, pre code, blockquote {
  border-radius: 0.5em;
}
blockquote {
  background-color: var(--bg-secondary);
  border: 1px var(--border) solid;
}
```

Mauris viverra dictum ultricies. Vestibulum quis ipsum euismod, facilisis metus sed, varius ipsum. Donec scelerisque lacus libero, eu dignissim sem venenatis at. Nunc a egestas tortor, sed feugiat leo.

## Table of contents
- [Table of contents](#table-of-contents)
- [The start](#the-start)
- [The middle](#the-middle)
- [The end](#the-end)

Mauris viverra dictum ultricies. Vestibulum quis ipsum euismod, facilisis metus sed, varius ipsum. Donec scelerisque lacus libero, eu dignissim sem venenatis at. Nunc a egestas tortor, sed feugiat leo. Vestibulum porta tincidunt tellus, vitae ornare tortor. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Sed nunc neque, tempor in iaculis non, faucibus et metus. Etiam id nisl ut lorem gravida euismod.

## [The start](#the-start)

Fusce non velit cursus ligula mattis convallis vel at metus. Sed pharetra tellus massa, non elementum eros vulputate non. Suspendisse potenti. Quisque arcu felis, laoreet vel accumsan sit amet, fermentum at nunc. Sed massa quam, auctor in eros quis, porttitor tincidunt orci. Nulla convallis id sapien ornare viverra. Cras nec est lacinia ligula porta tincidunt. Nam a est eget ligula pellentesque posuere. Maecenas quis enim ac risus accumsan scelerisque. Aliquam vitae libero sapien. Etiam convallis, metus nec suscipit condimentum, quam massa congue velit, sit amet sollicitudin nisi tortor a lectus. Cras a arcu enim. Suspendisse hendrerit euismod est ac gravida. Donec vitae elit tristique, suscipit eros at, aliquam augue. In ac faucibus dui. Sed tempor lacus tristique elit sagittis, vitae tempor massa convallis.

## [The middle](#the-middle)

Proin quis velit et eros auctor laoreet. Aenean eget nibh odio. Suspendisse mollis enim pretium, fermentum urna vitae, egestas purus. Donec convallis tincidunt purus, scelerisque fermentum eros sagittis vel. Aliquam ac aliquet risus, tempus iaculis est. Fusce molestie mauris non interdum hendrerit. Curabitur ullamcorper, eros vitae interdum volutpat, lacus magna lacinia turpis, at accumsan dui tortor vel lectus. Aenean risus massa, semper non lectus rutrum, facilisis imperdiet mi. Praesent sed quam quis purus auctor ornare et sed augue. Vestibulum non quam quis ligula luctus placerat sed sit amet erat. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Fusce auctor, sem eu volutpat dignissim, turpis nibh malesuada arcu, in consequat elit mauris quis sem. Nam tristique sit amet enim vel accumsan. Sed id nibh commodo, dictum sem id, semper quam.

## The end

Donec ex lectus, tempus non lacinia quis, pretium non ipsum. Praesent est nunc, rutrum vel tellus eu, tristique laoreet purus. In rutrum orci sit amet ex ornare, sit amet finibus lacus laoreet. Etiam ac facilisis purus, eget porttitor odio. Suspendisse tempus dolor nec risus sodales posuere. Proin dui dui, mollis a consectetur molestie, lobortis vitae tellus. Vivamus at purus sed urna sollicitudin mattis. Mauris lacinia libero in lobortis pulvinar. Nullam sit amet condimentum justo. Donec orci justo, pharetra ut dolor non, interdum finibus orci. Proin vitae ante a dui sodales commodo ac id elit. Nunc vel accumsan nunc, sit amet congue nunc. Aliquam in lacinia velit. Integer lobortis luctus eros, in fermentum metus aliquet a. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.




---
{: data-content="footnotes"}

[^1]: this is a footnote. You should reach here if you click on the corresponding superscript number.
[^2]: hey there, don't forget to read all the footnotes!
[^3]: this is another footnote.
[^4]: this is a very very long footnote to test if a very very long footnote brings some problems or not; hope that there are no problems but you know sometimes problems arise from nowhere.
