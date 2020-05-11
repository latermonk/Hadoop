#  Python版本的 MR 
 
hadoop2.7运行python编写的wordcount的MapReduce程序   
https://blog.csdn.net/Fourierrr_/article/details/80053877   

##  The First example 

**mapper.py**


```
#!/usr/bin/python3
# -*- coding: utf-8 -*-

"""mapper.py"""
import os
import sys
import re

for line in sys.stdin:
	line = line.strip()
	words = re.split('[,.?\s"]',line)
	for word in words:
		word = word.strip(',|.|?|\s')
		if word:

			print("{0}\t{1}".format(word,1))

```

**reducer.py**

```
#!/usr/bin/env python
# -*- coding: utf-8 -*-

"""resucer.py"""
import os
import sys
from operator import itemgetter
current_word = None
current_count = 0
word = None

for line in sys.stdin:
	word = line.split('\t',1)[0]
	count = line.split('\t',1)[1]
	count = int(count)
	if current_word == word:
		current_count+=count
	else:
		if current_word:
			print("{0}\t{1}".format(current_word,current_count))
		current_word = word
		current_count = count

if word:
	print("{0}\t{1}".format(current_word,current_count))



```

**本地测试**
```
echo "you? you, wow. Are uou you ok la " | ./mapper.py | sort |  ./reducer.py
```


**hadoop集群上进行测试**
```
bin/hadoop jar share/hadoop/tools/lib/hadoop-streaming-3.2.1.jar \
-file /home/ubuntu/abc/python/mapper.py -mapper /home/ubuntu/abc/python/mapper.py  \
-file /home/ubuntu/abc/python/reducer.py -reducer /home/ubuntu/abc/python/reducer.py  \
-input /test/*  -output /test_out1
```





