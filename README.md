# CPP_STL
# Competitive

Created: Jan 26, 2021 4:53 PM
Updated: Jan 27, 2021 4:49 PM

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

# Sorting - using #include\<algorithm> && #include\<string\>

 

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

> v.capacity()

> v.max_size()

> v.resize() → resize the size of vector

> v.empty() → return boolean if vector is empty

> v.clear() → remove all the elements from vector

> v.front()

> v.back()

> v.reserve() → makes the capacity constant to n

> v.erase(position) → position is a pointer(find it by iterator), v.erase(start_pos,end_pos)

> v.insert(pointer,element)

v.erase(std::remove(v.begin(),v.end(),5),v.end()); // #include<algorithm> 

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
