Standard Template Library
=============
##1 Sequence
###1.1 vector
+ class
 - vector<type> name(size,value);
 - vector<type> name(mtvector);
 - vector<type> name(first,last);
+ member
 - front(),back() 
 - begin(),end() 
 - clear() 
 - empty()
 - erase(i),erase(start,end)
 -  insert(i,x),insert(i,n,x),insert(i,start,end)
 - push_back(),pop_back()
 - size()

###1.2 deque
+ class
 - deque<type> name(size,value);
 - deque<type> name(mtvector);
 - deque<type> name(first,last);
+ member
 - front(),back() 
 - begin(),end() 
 - clear() 
 - empty()
 - erase(i),erase(start,end)
 - insert(i,x),insert(i,n,x),insert(i,start,end)
 - push_back(),pop_back(),push_front(),pop_front()
 - size()
 
####1.3 list
+ class
 - list<type> name(size,value);
 - list<type> name(mtvector);
 - list<type> name(first,last);
+ member
 - front(),back() 
 - begin(),end() 
 - clear() 
 - empty()
 - erase(i),erase(start,end)
 - insert(i,x),insert(i,n,x),insert(i,start,end)
 - push_back(),pop_back(),push_front(),pop_front()
 - size()
 - remove(val)
 - sort()

##2 Container Adapter
###2.1 stack
+ class
 - stack<type,container> name;
 - stack<int,list<int>> intStack;
+ member
 - empty(),size(),top(),push(),pop()
 
###2.2 queue
+ class
 - queue<type,container> name;
 - queue<int,list<int>> intQueue;
+ member
 - empty(),size(),front(),back(),push(),pop()

###2.3 priority_queue
+ class
 - priority_queue<type,container,predicate> name;
 - priority_queue<int,list<int>> intQueue;
+ member
 - empty(),size(),front(),back(),push(),pop()

## 3 Set Container
###3.1 set
+ class
 - set<type,predicate> name;
 - set<type,predicate> name(myset);
 - set<type,predicate> name(first,last);
 - set<int,less<int>> intset;
+ member
 - begin(),end() 
 - clear() 
 - empty()
 - cout(x)
 - erase(i),erase(start,end)
 - insert(i,x),insert(i,n,x),insert(i,start,end)
 - find(x)
 - size()

###3.2 multiset
+ class
 - multiset<type,predicate> name;
 - multiset<type,predicate> name(myset);
 - multiset<type,predicate> name(first,last);
 - multiset<int> intset;
+ member
 - begin(),end() 
 - clear() 
 - empty()
 - cout(x)
 - erase(i),erase(start,end)
 - insert(i,x),insert(i,n,x),insert(i,start,end)
 - find(x)
 - size()

###3.3 map
+ class
 - map<key,type,predicate> name;
 - map<key,type,predicate> name(myset);
 - map<key,type,predicate> name(first,last);
 - typedef map<int,char> mymap;
+ member
 - begin(),end() 
 - clear() 
 - empty()
 - cout(x)
 - erase(i),erase(start,end)
 - insert(i,x),insert(i,n,x),insert(i,start,end)
 - find(x)
 - size()
+ 其他
 - mymap[2]='A';

####3.4 multimap
+ class
 - multimap<key,type,predicate> name;
 - multimap<key,type,predicate> name(myset);
 - multimap<key,type,predicate> name(first,last);
+ member
 - begin(),end() 
 - clear() 
 - empty()
 - cout(x)
 - erase(i),erase(start,end)
 - insert(i,x),insert(i,n,x),insert(i,start,end)
 - xfind(x)
 - size()
(3)其他
charmap.insert(MYMAP::value_type(1,'A'));

####3.5 bitset
+ class
 - bitset<size> name;
 - bitset<size> name(value);
 - bitset<size> name(str,pos,n);
 - bitset<8> bit;
+ member
 - any(),cout(x),none(),set(),reset(),size(),test()

##4 Algorithm

###4.1 non-modify
- adjacent_find(first,last) 返回第一对相邻元素指示器
- count(first,last,val)  val出现的次数
- find(first,last,val) 返回val指示器

###4.2 modidfy

- copy(first,last,firsrt2) 复制到first2指向的容器
- fill(first,last,val) val填充容器
- generate(first,last,func）
- partition(first,last,pred)
- random_shuffle(first,last)
- reverse(first,last)
- swap(iter1,iter2)

###4.3 sort

- bool binary_search(first,last,val) 折半查找
- lower_bound(first,last,val) 有序元素查找，返回指示器
- max(val1,val2),min(val1,val2)
- max_element(first,last),min_element(first,last) 返回元素
- sort(first,last),stable_sort(first,last)

##5示例

```
#include"utility.h"
//定义谓词
class compare
{
public:
	bool operator()(const int c1,const int c2)const
	{
		cout<<"compare..."<<c1<<-c2<<endl;
		return c1<c2;
	}
};

int main()
{
	map<int,char,compare> charMap;
	cout<<"Adding...(1 A)"<<endl;
	for(int i=0;i<6;i++)
	{
	int key;
	char ch;
	cin>>key>>ch;
	charMap[key]=ch;
	}
	cout<<"Contents of maps..."<<endl;
	for(map<int,char,compare>::iterator iter=charMap.begin();iter!=charMap.end();iter++)
		cout<<iter->first<<"--"<<iter->second<<endl;
	system("pause");
	return 0;
}
```

