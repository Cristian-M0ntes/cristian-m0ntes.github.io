---

layout: post
---

netsh advfirewall firewall add rule name="Open port 9000" protocol=TCP dir=in action=allow localport=9000
netsh advfirewall firewall show rule all

reg add "HKEY_LOCAL_MACHINE\SYSTEM\currentControlSet\Control\Terminal Server" /v fDenyTSConnections \t REG_DWORD /d 0 /f

wevtutil el
wevtutil cl Ejemplo

#en powershell 
wevtutil el | Foreach-Object {wevtutil cl "$_"}


{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
