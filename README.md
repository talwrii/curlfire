# curlfire
Run curl with the current firefox cookies. This is useful for interacting with logged in websites.

# Attribution

This code is Adapted from [this Stack Exchange answer](https://superuser.com/questions/666167/how-do-i-use-firefox-cookies-with-wget)
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

# Alternative and prior work

* Adapted from [this stack overflow answer](https://superuser.com/questions/666167/how-do-i-use-firefox-cookies-with-wget)
* Firebug and friends allow you to copy requests as curl. This can be suitable for debugging.
* Cookies can be exported manually from within firefox

All of these approaches can be problematic when automating tasks.

