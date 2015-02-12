# js-trie-patricia
Patricia Trie for ip longest prefix matching in JavaScript

It works by adding ip subnet masks to the trie and find the longest prefix matching subnet for an ip in the provided list

example:
  ```javascript
  var tp = Trie.Patricia();
  tp.set_subnet("10.0.0.0/8","use_data1");
  tp.set_subnet("10.0.0.0/16","use_data2");
  tp.set_subnet("10.0.0.0/24","use_data3");
  tp.get_ip("10.0.0.1"); // should return "user_data3"
  tp.get_ip("10.0.1.1"); // should return "user_data2"
  tp.get_ip("10.1.1.1"); // should return "user_data1"
  
  tp.set_subnet("192.168.1.0/24",["192.168.1.0/24", "data1"]);
  tp.set_subnet("127.0.0.0/8", ["127.0.0.0/8", "data2"]);
  data = tp.get_ip("127.0.0.1");
  console.log(data[0]); // matching subnet - "127.0.0.0/8"
  console.log(data[1]); // matching data - "data2"
  tp.del_subnet("127.0.0.0/8"); 
  ```
Note that the set, get and del are the only functionality that are working with IPs, other trie-patricia methods will not work
