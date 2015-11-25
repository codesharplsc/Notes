###C++ STL

Container：To store certain data

####string
To store string-like data structure.However, this data structure is not the same as the char string in original C++

**\#include\<string>**


Define：
 
	string 	s1;s1 = "value";
	string  s2(s1);			//construct with s1
	string 	s1("value");	//construct with "value" string
	string	s1(n,'d');		//initialize n-length string with 'd' element
Operation:

	s1.empty();				//return true or false
	s1.size();s1.length();	//return length of the string
	s1+s2					//concatenate
	s1==s2					//compare
	cin>>s1;				//read
	getline(cin.s1);		//read from io stream
In size(),length(),the return value is `size_type`. This true value is determined according to specific compiling environment，usually`unsigned int`or`unsigned long`.To use this specific data type,

	string::size_type length;
	
####vector
Similar to string type, this data structure can be used to store certain kinds of data. Its most advantage over array or dynamic pointer is that it can grow dynamically.

**\#include\<vector>**

Define:

	vector<T> v1;		//T is the actual data type
	vector<T> v2<v1>;
	vector<t> v1(n,i);	//construct n element, type T, with value i
	vector<T> v1(n);	//construct n element,their type is T

Operation:

	v1.size();
	v1.push_back(a);					 //add the element to the rear position
	v1.insert(v1.begin()+i,a);	     //insert "a" before the v1[i].v1.begin means the start element, v1.insert(v1.begin(),a) will insert a to be the first element				
	v1.erase(v1.begin()+2);				//delete the third element 
	v1.erase(v1.begin()+i,v1.end()+j);//delete range[i,j-1]
Except `push_back` function, others' argument must be an iterator, this will be illustrated below.
	
	vector<T>::size_type length;
	
####Iterator
Iterator is like the pointer to a data structure. It can be used to reference to a certain element in a container.
	
	vector<T>::iterator iter = v1.begin();//iter point to v1[0],*iter equals to v1[0],v1.end() points to the element after the next element,which is not included in the container.
	vector<T>::const_iterator iter1 = v1.begin();//this iter1 can only reference to the element in the container,but can't modify them  
	


 
	
