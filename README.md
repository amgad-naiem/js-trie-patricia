# js-trie-patricia
Patricia Trie for ip longest prefix matching in JavaScript

It works by adding ip subnet masks to the trie and find the longest prefix matching subnet for an ip in the provided list

example:
  '''
  var tp = Trie.Patricia();
  tp.set_subnet("10.0.0.0/8","use_data1");
  tp.set_subnet("10.0.0.0/16","use_data2");
  tp.set_subnet("10.0.0.0/24","use_data3");
  tp.get("10.0.0.1"); // should return "user_data3"
  tp.get("10.0.1.1"); // should return "user_data2"
  tp.get("10.1.1.1"); // should return "user_data1"
  
  tp.add("192.168.1.0/24")
  pt.add("127.0.0.0/8", "user_data")
  node = pt.search_best("127.0.0.1")
  puts node.data
  puts node.prefix
  puts node.network
  puts node.prefixlen
  pt.remove("127.0.0.0/8")
  '''
