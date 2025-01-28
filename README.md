# curlfire
@readwithai - [X](https://x.com/readwithai) - [blog](https://readwithai.substack.com)

Run curl with the current [Firefox](https://www.mozilla.org/en-US/firefox/) cookies.
This is useful for interacting with logged in websites from the shell, without having to manually deal with the login process.

The executable `cookiefire` included in this package can be used to extract the cookies from Firefox.

This is achieved by reading the **cookies.sqlite** file in Firefox profiles.

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

# Caveats
* **Does not work with session cookies**[(1)](https://support.mozilla.org/en-US/questions/899388
) (you may be able to work around this by setting "Remember me" for the website with which you are using your tool)
* Only tested on linux machines
* Unlikely to work with windows
* Will probably work on macs but untested (feedback welcome)

# Installation
```
cd ~
git clone https://github.com/talwrii/curlfire
echo 'PATH=$PATH:~/curlfire' >> ~/.bashrc
```

# Alternatives and prior work
* Adapted from [this Stack Exchange answer](https://superuser.com/questions/666167/how-do-i-use-firefox-cookies-with-wget)
* Firebug and friends allow one to copy requests as curl commands. This can be suitable for debugging.
* Cookies can be exported manually from within Firefox

All of these approaches can be time consuming when automating tasks.

[Prior to Firefox 57](https://support.mozilla.org/en-US/kb/frequently-asked-questions-firefox-addon), the [remote control extension](https://addons.mozilla.org/en-US/firefox/addon/remote-control/) could be used to interact with the page currently viewed in Firefox from the shell (including outputting the current [document object model](https://en.wikipedia.org/wiki/Document_Object_Model) as HTML).

# Complementary projects (and shameless advertising)
Users of this project might also be interested in:

* [clixpath](https://github.com/talwrii/clixpath) (by author) - an open-source tool for extracting information out of HTML documents in machine-readable JSON using [Xpath](https://www.w3.org/TR/1999/REC-xpath-19991116/).
* [PhantomJs](http://phantomjs.org/) - a scriptable command-line only browser than can be used to [render the document object model in Javascript based-websites](https://stackoverflow.com/a/9978162) and output more easily processed HTML.

 # Copyright
This code is distributed under [an MIT license](LICENSE).
It contains code adapted from a code snippet in the aforementioned Stack Exchange answer which is also distributed under [an MIT license](SNIPPET-LICENSE) as [stipulated by the Stack Exchange terms and conditions](https://meta.stackexchange.com/questions/272956/a-new-code-license-the-mit-this-time-with-attribution-required).

# About me 
I am [@readwithai](https://x.com/readwithai). I make tools for [productivity](https://readwithai.substack.com/p/obsidian-plugin-repl) and agency particularly related to deep reading and using [Obsidian](https://readwithai.substack.com/p/what-exactly-is-obsidian). If this sounds interesting you can follow me on [X](https://x.com/readwithai) or [substack](https://readwithai.substack.com). 

If you find *this* piece of software useful you could consider paying me 2 dollars on my [ko-fi](https://ko-fi.com/readwithai).


