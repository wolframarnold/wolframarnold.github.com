---
layout: default
title: "Unfaithful Mime Types: Ajax, jQuery and Rails"
---

Hi
==

On redirect, FF Ajax loses accept header MIME type and drops back to text/html

What works, though is redirecting to a URL that has a ".:format" parameter set to, e.g. "json".  That will provoke a redirect to the JSON-URL, and the server will correctly parse it via respond_to {|format| format.json {render :json => ...} }


