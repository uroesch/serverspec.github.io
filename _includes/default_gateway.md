### <a name="default_gateway">default_gateway</a>

Default gateway resource type.

In order to test a default gateway is set up correctly, you should use this syntax.

```ruby
describe default_gateway do
  its(:ipaddress) { should eq '192.168.10.1' }
  its(:interface) { should eq 'br0'          }
end
```

To run checks against the IPv6 default gateway, use the following syntax. 

```ruby
describe default_gateway do
  its(:ipv6_ipaddress) { should eq '2001:db8::1' }
  its(:ipv6_interface) { should eq 'br0'          }
end
```

One can also explicity use the IPv4 prefix.

```ruby
describe default_gateway do
  its(:ipv4_ipaddress) { should eq '192.168.10.1' }
  its(:ipv4_interface) { should eq 'br0'          }
end
```
