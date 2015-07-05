### <a name="default_gateway">default_gateway</a>

Default gateway resource type.

In order to test a default gateway is set up correctly, you should use this syntax.

```ruby
describe default_gateway do
  its(:ipaddress) { should eq '192.168.10.1' }
  its(:interface) { should eq 'br0'          }
end
```

The above sample only operates on the IPv4 stack. To get the IPv6 default gateway, prefix either keyword with _ipv6\__. 
If the IPv6 default route is a link local address they scope ID e.g. _%eth0_ is ommited. 

```ruby
describe default_gateway do
  its(:ipv6_ipaddress) { should eq '2001:db8::1' }
  its(:ipv6_interface) { should eq 'br0'          }
end
```

An IPv4 prefix is also available.

```ruby
describe default_gateway do
  its(:ipv4_ipaddress) { should eq '192.168.10.1' }
  its(:ipv4_interface) { should eq 'br0'          }
end
```
