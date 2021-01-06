
# URL Schemes

## Preface

### Supported Schemes (URL Prefixes)
#### spring
The URL can be opened in a older version of Spring, which version may not support these URL Schemes.

#### spring2
The URL can be opened only if Spring has been updated to a supported version.

### Common Parameters
#### account
Perform a task with specific account identified by your account name (user screen name). The value of account is case insensitive.

For example, the account name of @theSpringApp is "theSpringApp".

#### account-id
Perform a task with specific account identified by the numeric Twitter User ID. 

To get your user ID, first open your user page, then tap the Action button on upper right corner, then tap Copy and select Copy User ID.

Generally, you only need to provide either `account` or `account-id` unless otherwise specified in this document.

"account-id" is preferred over "account" because the ID is a stable value linked to your Twitter account, while the account name can be changed at anytime at Twitter.com, which means if you use "account-id" instead of "account", you don't have to update your URL Scheme configurations after you change your Twitter account name.

## Switch Account
Provide "account" or "account-id" as parameter. Nothing changed if the target account is already activated on the current app window.

#### Examples:
spring2://switch?account=theSpringApp

spring2://switch?account-id=886626176751546368

## Open Tweet Composer
You can provide 2 optional parameters: text, account/account-id

The value of text parameter will be filled into the tweet composer view. If no account provided, Spring chooses a default account based on the current app window.

#### Examples:
spring2://post?text=hello

spring2://post?text=hello&account-id=886626176751546368

## Open Search View
You can provide 2 optional parameters: text, account/account-id

The value of text parameter will be filled into the search bar.

### Examples:
spring2://search?text=hello

spring2://search?text=hello&account-id=886626176751546368

## Open Twitter Links
Currently supports links to tweets (e.g. https://twitter.com/thespringapp/status/1344625888449556480), user pages (e.g. https://twitter.com/thespringapp), and Twitter Lists (e.g. https://twitter.com/i/lists/1344918930687729664)

### Basic
Replace the “https” prefix in a Twitter URL with “spring”.

For example, open @theSpringApp’s user page using default account: 

spring://twitter.com/theSpringApp

### Advanced
Use the “open” URL scheme if you want to open multiple pages at once, or open a page with specific account.

The URL takes 2 parameters: url (required), and account/account-id (optional).

You may include multiple url parameters. "url" parameters must be percent encoded.

For example, open user page of @twitter and @jack with a signed in account called @theSpringApp would be something like this: 

spring://open?account=theSpringApp&url=https%3A%2F%2Ftwitter.com%2Ftwitter&url=https%3A%2F%2Ftwitter.com%2Fjack
