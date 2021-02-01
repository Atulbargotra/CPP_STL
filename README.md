# Competitive

Created: Jan 26, 2021 4:53 PM
Tags: competitive, cpp, stl
Updated: Feb 1, 2021 4:32 PM

# **#include\<algorithm\>**

## Find Function-

find the target elements memory address in O(n) time.

```cpp
#include<algorithm>
int main(){
    int arr[] = {10,20,45,40};
    int n = sizeof(arr)/sizeof(int);
	int target = 40;
    auto pt = find(arr,arr+n,target);
int index = pt-arr;
cout<<index;
}
```

## binary_search function-

find the memory address of the target element if the array is sorted in O(logn) time.

```cpp
#include<algorithm>
int main(){
    int arr[] = {10,20,45,40};
    int n = sizeof(arr)/sizeof(int);
	int target = 40;
    auto pt = binary_search(arr,arr+n,target);
int index = pt-arr;
cout<<index;
}
```

## upper_bound and lower_bound

upper_bound - find the memory address of the element (≥) the target.

 lower_bound - find the memory address of the element (>) the target.

```cpp
#include <iostream>
#include<algorithm>
using namespace std;
int main() {
    int arr[] = {10,20,30,40};
    int n = sizeof(arr)/sizeof(int);
    auto it = lower_bound(arr,arr+n,440);
    auto up = upper_bound(arr,arr+n,440);
    cout<<(it-arr);
    cout<<(up-arr);
}
```

# #include\<string\>

> s.empty() → return boolean value if string is empty

> s.append()

> s.length()

> s.clear() → clears the string

> s.compare(s2) → return  +ve or -ve value according to lexicographical comparison and if same returns 0

> s.find(string) → returns the index of the first occurrence.

> s.erase(start,end) → removes characters in string from start to end position.

```cpp
//iterator for strings.
for(string::iterator it= s.begin();it!=s.end();it++){
cout<<(*it);
}

//string::iterator it -> auto it

for(auto it= s.begin();it!=s.end();it++){
cout<<(*it);
}

for(char i: s){
cout<<i;
}

```

# Sorting - using #include\<algorithm\> && #include\<string\>

 

```cpp
#include <iostream>
#include<algorithm>
#include<string>
using namespace std;
bool compare(string a,string b){
    if(a.length() == b.length()) return a<b;
    return a.length()>b.length();
}
int main() {
    int n;
    cin>>n;
    cin.get();
    string arr[100];
    for(int i = 0;i<n;i++){
        getline(cin,arr[i]);
    }
    sort(arr,arr+n,compare);
     for(int i = 0;i<n;i++){
        cout<<arr[i]<<endl;
    }
}
```

# Tokenizing a string using strtok

char *strtok(char *str, const char *delim)

```cpp

#include <iostream>
#include<cstring>
using namespace std;
bool compare(string a,string b){
    if(a.length() == b.length()) return a<b;
    return a.length()>b.length();
}
int main() {
   char s[100] = "hello my name is atul";
   char *ptr = strtok(s," ");
   cout<<ptr<<endl;
   while(ptr!=NULL){
       ptr = strtok(NULL," ");
       cout<<ptr<<endl;
   }
}
```

# Vectors

```cpp
vector<int>v;
vector<int>v1(5,10);
vector<int>v2(v1);
vector<int>v3{10,20,30};

v.size();
v.capacity();
v.max_size();

```

> v.push_back()

> v.pop_back()

> v.size()

> v.capacity() → returns the maximum number of elements that can be held by the vector at that instance tip→ vector double its space if current_size is less.

> v.max_size() → returns the maximum number of elements that can be held by the vector container.

> v.resize() → resize the size of vector

> v.empty() → return boolean if vector is empty

> v.clear() → remove all the elements from vector

> v.front() → returns an integer at index 0

> v.back() → returns an integer at index -1

> v.reserve() → makes the capacity constant to n

> v.erase(position) → position is a pointer(find it by iterator), v.erase(start_pos,end_pos)

> v.insert(pointer,element)

v.erase(std::remove(v.begin(),v.end(),5),v.end()); // #include<algorithm>  if want to remove all ocurance use v.end as econd param to erase else it will remove the first occurance only.

# List → double linked list

```cpp
#include<list>
list<int>l{1,2,3,4,1};
l.push_back();
l.pop_back();
l.push_front();
l.pop_front();
l.erase(pointer);
l.remove(element);
l.insert(pointer,element);
```

# Stack:

```cpp
#include <iostream>
#include<stack>
using namespace std;
int main() {
    stack<int>s;
    s.push(5);
    s.push(10);
    while(!s.empty()){
        cout<<s.top();
        s.pop();
    }
}

Output:
10->5
```

# Queue:

```cpp
#include <iostream>
#include<queue>
using namespace std;
int main() {
    queue<int>q;
    q.push(5);
    q.push(10);
    while(!q.empty()){
        cout<<q.front();
        q.pop();
    }
}

Output:
5->10
```

# Priority Queue(implemented using heap)

push() && pop() takes O(LogN) time. and top() takes O(1).

```cpp
#include <iostream>
#include<queue>
using namespace std;
int main() {
    priority_queue<int>pq; //max heap
    //priority_queue<int,vector<int>,greater<int>>pq; minHeap
    pq.push(5);
    pq.push(10);
    while(!pq.empty()){
        cout<<pq.top();
        pq.pop();
    }
}

Output:
10->5
```

Class based comparators

```cpp
#include <iostream>
#include<queue>
using namespace std;
class Person{
    public:
    int age;
    string name;
    Person(){

    }
    Person(string n,int a){
        name = n;
        age = a;
    }
};
class PersonComp{
    public:
    bool operator()(Person A,Person B){
        return A.age < B.age;
    }
};
int main() {
    priority_queue<Person,vector<Person>,PersonComp>pq;
    int n;
    cin>>n;
    for(int i=0;i<n;i++){
        int age;
        string name;
        cin>>name>>age;
        Person p(name,age);
        pq.push(p);
    }
    for(int i=0;i<3;i++){
        Person p = pq.top();
        cout<<p.name<<" "<<p.age;
        pq.pop();
    }
}
```

# Maps

```cpp
#include <iostream>
#include<map>
#include<string>
using namespace std;
int main() {
    map<string,int>m;
    //1. insert
    m.insert(make_pair("mango",140));
    //using pair
    pair<string,int>p;
    p.first = "apple";
    p.second = 178;
    m.insert(p);
    //direct assignment
    m["orange"] = 156;

    //2. find 
    auto pt = m.find("apple");
    if(pt!=m.end()){
        cout<<"found"<<m["apple"];
    }
    else cout<<"not found";

    //another way to find if key is present
    if(m.count("mango")){
        cout<<"found";
    }
    else cout<<"not found";

    //3. erasing key-value pair
    m.erase("mango");

    //4. Updating values
    m["apple"]+=40;

    cout<<m["apple"];

    //5. iterating over keys and values

    for(auto it=m.begin();it!=m.end();it++){
        cout<<it->first<<" "<<(*it).second<<endl;
        //(*it).first
    }

    for(auto p: m){
        cout<<p.first<<" "<<p.second<<endl;
    }

}
```

# Multi map

```cpp
#include <iostream>
#include<map>
#include<string>
using namespace std;
int main() {
    multimap<char,string>m;
    //1. insert
    m.insert(make_pair('a',"apple"));
    //using pair
    pair<char,string>p;
    p.first = 'a';
    p.second = "acer";
    m.insert(p);
    //direct assignment
    m.insert(make_pair('b',"ball"));
    m.insert(make_pair('b',"bat"));
    m.insert(make_pair('c',"cat"));
    m.insert(make_pair('d',"dog"));
    //2. find 
    auto pt = m.find('b');
    if(pt!=m.end()){
        m.erase(pt);
    }
    else cout<<"not found";
    //3. iterating over keys and value

    for(auto p: m){
        cout<<p.first<<" "<<p.second<<endl;
    }

    auto it1 = m.lower_bound('b');
    auto it2 = m.upper_bound('d');
    for(auto it3 = it1;it3!=it2;it3++){
        cout<<it3->second;
    }
}
```

# Unordered map for our custom class

```cpp
#include <iostream>
#include<unordered_map>
#include<string>
using namespace std;
class student{
    public:
    string fname,sname,rollno;
    student(string fname,string sname,string rollno){
        this->fname = fname;
        this->sname = sname;
        this->rollno = rollno;
    }
    bool operator==(const student &s) const{
        return rollno == s.rollno;
    }
};

class Hashf{
    public:
    size_t operator()(const student &s) const{
        return s.fname.length()+s.sname.length();
    }
    //size_t is a unsigned int datatype. it is used to represent size of some memory in bytes
};

int main() {
    unordered_map<student,int,Hashf>m;
    student s1("atul","verma","37");
    student s2("atul","verma","38");

    m[s1] = 140;
    m[s2] = 189;

    for(auto p: m){
        cout<<p.first.fname<<" "<<p.second;
    }
    //find value using key
    cout<<m[s2];
}
```

# Set

```cpp
//fira code ligations 

#include <iostream>
#include<set>
using namespace std;
int main() {
    set<int>s;
    int arr[] = {4,5,5,7,8};
    int n = sizeof(arr)/sizeof(int);
    for(int i=0;i<n;i++){
        s.insert(arr[i]);
    }
    s.erase(4);

    auto it = s.find(5);
    s.erase(it);
    for(set<int>::iterator it = s.begin();it!=s.end();it++){
        cout<<(*it)<<",";
    }
}
```

# Multi Set

```cpp
#include <iostream>
#include<set>
using namespace std;

typedef multiset<int>::iterator Itt;

int main() {
    multiset<int>s;
    int arr[] = {4,5,5,7,8,10,10,100,4};
    int n = sizeof(arr)/sizeof(int);
    for(int i=0;i<n;i++){
        s.insert(arr[i]);
    }
    s.erase(4);

    auto it = s.find(5);
    s.erase(it);
    for(set<int>::iterator it = s.begin();it!=s.end();it++){
        cout<<(*it)<<",";
    }

    //finding pointer to same elemets -> equal_range

    pair<Itt,Itt> p = s.equal_range(10);
    for(auto it = p.first;it!=p.second;it++){
        cout<<*it;
    }

    //count
    cout<<s.count(10);

    //find
    it = s.find(10);
    cout<<*it;

    //upper_bouund and lower_bound 

}
```

# Policy based data structures

```cpp
#include<bits/stdc++.h>

#include <ext/pb_ds/assoc_container.hpp>
#include <ext/pb_ds/tree_policy.hpp>

using namespace std;
using namespace __gnu_pbds;

typedef tree<int, null_type, less<int>, rb_tree_tag, tree_order_statistics_node_update> PBDS;
int main() {
	freopen("input.txt", "r", stdin);
	freopen("output.txt", "w", stdout);

	PBDS St;
	St.insert(1);
	St.insert(3);
	St.insert(4);
	St.insert(10);
	St.insert(15);
	for (int i = 0; i < (int)St.size(); i++) {
		cout << i << " " << *St.find_by_order(i) << endl;
	}
	//find_by_order => at given index what is the value or kth largest element till now

	//order_of_key => how many elements are there which are smaller than n or index at which we can insert in the set
	
	cout << St.order_of_key(5);
	return 0;
}
```

```cpp
//if we want to insert same values in the set then we can use pair<value,index>
//typedef tree<pair<int,int>, null_type, less<pair<int,int>>, rb_tree_tag, tree_order_statistics_node_update> PBDS;
#include<bits/stdc++.h>

#include <ext/pb_ds/assoc_container.hpp>
#include <ext/pb_ds/tree_policy.hpp>

using namespace std;
using namespace __gnu_pbds;

typedef tree<pair<int, int>, null_type, less<pair<int, int>>, rb_tree_tag, tree_order_statistics_node_update > PBDS;
int main() {
	freopen("input.txt", "r", stdin);
	freopen("output.txt", "w", stdout);

	PBDS St;
	St.insert({1, 0});
	St.insert({2, 1});
	St.insert({2, 2});
	for (int i = 0; i < (int)St.size(); i++) {
		cout << i << " " << St.find_by_order(i)->first << " " << St.find_by_order(i)->second << endl;
	}
	//find_by_order => at given index what is the value or kth largest element till now in logn

	//order_of_key => how many elements are there which are smaller than n or index at which we can insert in the set in logn

	//insertion in set takes logn

	cout << St.order_of_key({5,100000});

	return 0;
}
```
