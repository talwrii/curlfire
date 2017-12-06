# curlfire
Run curl with the current [Firefox](https://www.mozilla.org/en-US/firefox/) cookies. 
This is useful for interacting with logged in websites from the shell, without having to manually deal with the login process.

The executable `cookiefire` included in this package can be used to extract the cookies from Firefox.

# Attribution

This code is adapted from [this Stack Exchange answer](https://superuser.com/a/1239036/653515) by [hackerb9](https://superuser.com/users/400780/hackerb9).

# Usage

```
# Fetch google with the cookies from the default profile
curlfire http://www.google.com/

# Fetch google with the cookies from the blah profile
curlfire -P blah http://www.google.com/

# Getting cookies
cookiefire > /tmp/cookies
curl -b /tmp/cookies http://www.google.com/
```

# Installation
```
cd ~
git clone https://github.com/talwrii/curlfire
echo 'PATH=$PATH:~/curlfire' >> ~/.bashrc
```

# Alternatives and prior work

* Adapted from [this Stack Exchange answer](https://superuser.com/questions/666167/how-do-i-use-firefox-cookies-with-wget)
* Firebug and friends allow you to copy requests as curl. This can be suitable for debugging.
* Cookies can be exported manually from within Firefox

All of these approaches can be time consuming when automating tasks.

[Prior to Firefox 57](https://support.mozilla.org/en-US/kb/frequently-asked-questions-firefox-addon), the [remote control extension](https://addons.mozilla.org/en-US/firefox/addon/remote-control/) could be used to interact with the page currently viewed in Firefox from the shell (including outputting the current [document object model](https://en.wikipedia.org/wiki/Document_Object_Model) as HTML).
