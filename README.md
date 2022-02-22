# data-structure
Write a C++ program for implementing Singly Linked list.
//write a program to impliment the single linked list

#include<iostream> 
#include<cstdlib> 
using namespace std;<br> 
struct node <br> 
{ 
 int info; <br> 
 struct node *next; <br> 
}*start; <br> 
class single_llist <br> 
{ 
 public: <br> 
 node* create_node(int); <br> 
 void insert_begin(); <br> 
 void insert_last();<br>  
 void insert_pos(); <br> 
 void delete_begin(); <br> 
 void delete_last(); <br> 
 void delete_pos(); <br> 
 void update_begin(); <br> 
 void update_last(); <br> 
 void update_pos(); <br> 
 void sort(); <br> 
 void reverse(); <br> 
 void search(); <br> 
 void display(); <br> 
 single_llist() <br> 
 { 
 start = NULL; <br> 
 } 
}; 
int main() <br> 
{ 
 int choice; <br> 
 single_llist sl,s2; <br> 
 start = NULL; <br> 
 do <br> 
 { 
 cout<<"---------------------------------"<<endl; <br> 
 cout<<"Operations on singly linked list"<<endl; <br> 
 cout<<"---------------------------------"<<endl; <br> 
 cout<<"1.Insert at first"<<endl; <br> 
 cout<<"2.Insert at last"<<endl; <br> 
 cout<<"3.Insert at position"<<endl; <br> 
 cout<<"4.Delete at first"<<endl; <br> 
 cout<<"5.Delete at Last"<<endl; <br> 
 cout<<"6.Delete at position"<<endl; <br> 
 cout<<"7.Update at first"<<endl; <br> 
 cout<<"8.Update at last"<<endl; <br> 
 cout<<"9.Update at position"<<endl; <br> 
 cout<<"10.Ascending order"<<endl; <br> 
 cout<<"11.Descending order"<<endl; <br> 
 cout<<"12.Search"<<endl; <br> 
 cout<<"13.Display"<<endl; <br> 
 cout<<"14.Exit "<<endl; <br> 
 cout<<"Enter your choice :"; <br> 
 cin>>choice; <br> 
 switch(choice) <br> 
 { 
 case 1: sl.insert_begin(); <br> 
 sl.display(); <br> 
 break; <br> 
 case 2: sl.insert_last(); <br> 
 sl.display(); <br> 
 break; <br> 
 case 3: sl.insert_pos(); <br> 
 sl.display(); <br> 
 break; <br> 
 case 4: s2.delete_begin(); <br> 
 sl.display(); <br> 
 break; <br> 
 case 5: s2.delete_last(); <br> 
 sl.display(); <br> 
 break; <br> 
 case 6: sl.delete_pos(); <br> 
 sl.display(); <br> 
 break; <br> 
 case 7: sl.update_begin(); <br> 
 sl.display(); <br> 
 break; <br> 
 case 8: sl.update_last(); <br> 
 sl.display(); <br> 
 break; <br> 
 case 9: sl.update_pos(); <br> 
 sl.display(); <br> 
 break; <br> 
 case 10:sl.sort(); <br> 
 sl.display(); <br> 
 break; <br> 
 case 11:sl.reverse(); <br> 
 sl.display(); <br> 
 break; <br> 
 case 12:sl.search(); <br> 
 sl.display(); <br> 
 break; <br> 
 case 13:sl.display(); <br> 
 break; <br> 
 case 14:exit(0); <br> 
 break; <br> 
 default:cout<<"Wrong choice...???"<<endl; <br> 
 break; <br> 
 } 
 } 
 while(choice != 14); <br> 
} 
node *single_llist::create_node(int value) <br> 
{ 
 struct node *temp, *s; <br> 
 temp = new(struct node); <br> 
 if (temp == NULL) <br> 
 { 
 cout<<"Memory not allocated"<<endl; <br> 
 return 0; <br> 
 } 
 else <br> 
 { 
 temp->info = value; <br> 
 temp->next = NULL; <br> 
 return temp; <br> 
 } 
} 
void single_llist::insert_begin() <br> 
{ 
 int value; <br> 
 cout<<"Enter the value to be inserted : "; <br> 
 cin>>value; <br> 
 struct node *temp, *s; <br> 
 temp = create_node(value); <br> 
 if (start == NULL) <br> 
 { 
 start = temp; <br> 
 start->next = NULL; <br> 
 cout<<temp->info<<" is inserted at first in the empty list"<<endl; <br> 
 } 
 else <br> 
 { 
 s = start; <br> 
 start = temp; <br> 
 start->next = s; <br> 
 cout<<temp->info<<" is inserted at first"<<endl; <br> 
 } 
} 
void single_llist::insert_last() <br> 
{ 
 int value; <br> 
 cout<<"Enter the value to be inserted : "; <br> 
 cin>>value; <br> 
 struct node *temp, *s; <br> 
 temp = create_node(value); <br> 
 if (start == NULL) <br> 
 { 
 start = temp; <br> 
 start->next = NULL; <br> 
 cout<<temp->info<<" is inserted at last in the empty list"<<endl; <br> 
 } 
 else <br> 
 { 
 s = start; <br> 
 while (s->next != NULL) <br> 
 { 
 s = s->next; <br> 
 } 
 temp->next = NULL; <br> 
 s->next = temp; <br> 
 cout<<temp->info<<" is inserted at last"<<endl; <br> 
 } 
} 
void single_llist::insert_pos() <br> 
{ 
 int value, pos, counter = 0, loc = 1; <br> 
 struct node *temp, *s, *ptr; <br> 
 s = start; <br> 
 while (s != NULL) <br> 
 { 
 s = s->next; <br> 
 counter++; <br> 
 } 
 if (counter == 0){} <br> 
 else 
 { 
 cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : "; <br> 
 cin>>pos; <br> 
 s = start; <br> 
 if(pos == 1) <br> 
 { <br> 
 cout<<"Enter the value to be inserted : "; <br> 
 cin>>value; <br> 
 temp = create_node(value); <br> 
 start = temp;<br>  
 start->next = s; <br> 
 cout<<temp->info<<" is inserted at first"<<endl; <br> 
 } 
 else if (pos > 1 && pos <= counter) <br> 
 { 
 cout<<"Enter the value to be inserted : "; <br> 
 cin>>value; <br> 
 temp = create_node(value); <br> 
 for (int i = 1; i < pos; i++) <br> 
 { 
 ptr = s; <br> 
 s = s->next; <br> 
 } 
 ptr->next = temp; <br> 
 temp->next = s; <br> 
 cout<<temp->info<<" is inserted at position "<<pos<<endl; <br> 
 } 
 else if (pos == counter+1) <br> 
 { 
 cout<<"Enter the value to be inserted : "; <br> 
 cin>>value; <br> 
 temp = create_node(value); <br> 
 while (s->next != NULL) <br> 
 { 
 s = s->next; <br> 
 } 
 temp->next = NULL; <br> 
 s->next = temp; <br> 
 cout<<temp->info<<" is inserted at last"<<endl; <br> 
 } 
 else <br> 
 { 
 cout<<"Positon out of range...!!!"<<endl; <br> 
 } 
 } 
} 
void single_llist::delete_begin() <br> 
{ 
 if (start == NULL){} <br> 
 else <br> 
 { 
 struct node *s, *ptr; <br> 
 s = start; <br> 
 start = s->next; <br> 
 cout<<s->info<<" deleted from first"<<endl; <br> 
 free(s); <br> 
 } 
} 
void single_llist::delete_last() <br> 
{ 
 int i, counter = 0; <br> 
 struct node *s, *ptr; <br> 
 if (start == NULL){} <br> 
 else <br> 
 { 
 s = start; <br> 
 while (s != NULL) <br> 
 { 
 s = s->next; <br> 
 counter++; <br> 
 } 
 s = start; <br> 
 if (counter == 1) <br> 
 { 
 start = s->next; <br> 
 cout<<s->info<<" deleted from last"<<endl; <br> 
 free(s); <br> 
 } 
 else <br> 
 { 
 for (i = 1;i < counter;i++) <br> 
 { 
 ptr = s; <br> 
 s = s->next; <br> 
 } 
 ptr->next = s->next; <br> 
 cout<<s->info<<" deleted from last"<<endl; <br> 
 free(s); <br> 
 } 
 } 
} 
void single_llist::delete_pos() <br> 
{ 
 int pos, i, counter = 0, loc = 1; <br> 
 struct node *s, *ptr; <br> 
 s = start; <br> 
 while (s != NULL) <br> 
 { 
 s = s->next; <br> 
 counter++; <br> 
 } 
 if (counter == 0){} <br> 
 else 
 { 
 if (counter == 1) <br> 
 { 
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br> 
 cin>>pos; <br> 
 s = start; <br> 
 if (pos == 1) <br> 
 { 
 start = s->next; <br> 
 cout<<s->info<<" deleted from first"<<endl; <br> 
 free(s); <br> 
 } 
 else <br> 
 cout<<"Position out of range...!!!"<<endl; <br> 
 } 
 else <br> 
 { 
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br> 
 cin>>pos; <br> 
 s = start; <br> 
 if (pos == 1) <br> 
 { 
 start = s->next; <br> 
 cout<<s->info<<" deleted from first"<<endl; <br> 
 free(s); <br> 
 } 
 else if (pos > 1 && pos <= counter) <br> 
 { 
 for (i = 1;i < pos;i++) <br> 
 { 
 ptr = s; <br> 
 s = s->next; <br> 
 } 
 ptr->next = s->next; <br> 
 if(pos == counter) <br> 
 {cout<<s->info<<" deleted from last"<<endl; <br> 
 free(s);} <br> 
 else <br> 
 {cout<<s->info<<" deleted from postion "<<pos<<endl; <br> 
 free(s);} <br> 
 } 
 else <br> 
 cout<<"Position out of range...!!!"<<endl; <br> 
 } 
 } 
} 
void single_llist::update_begin() <br> 
{ 
 int value, pos=1, i,counter = 0; <br> 
 struct node *s, *ptr; <br> 
 s = start; <br> 
 while (s != NULL) <br> 
 { 
 s = s->next; <br> 
 counter++; <br> 
 } 
 if (counter == 0){} <br> 
 else if (pos == 1) <br> 
 { 
 cout<<"Enter the new node : "; <br> 
 cin>>value; <br> 
 start->info = value; <br> 
 cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl; <br> 
 } 
} 
void single_llist::update_last() <br> 
{ 
 int value, pos, i,counter = 0; <br> 
 struct node *s, *ptr; <br> 
 s = start; <br> 
 while (s != NULL) <br> 
 { 
 s = s->next; <br> 
 counter++; <br> 
 } 
 s=start; <br> 
 if (counter == 0){} <br> 
 else <br> 
 { 
 cout<<"Enter the new node : "; <br> 
 cin>>value; <br> 
 for (i = 1; i < counter ; i++) <br> 
 { 
 s = s->next; <br> 
 } 
 s->info = value; <br> 
 cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl; <br> 
 } 
} 
void single_llist::update_pos() <br> 
{ 
 int value, pos, i,counter = 0, loc = 1; <br> 
 struct node *s, *ptr; <br> 
 s = start; <br> 
 while (s != NULL) <br> 
 { 
 s = s->next; <br> 
 counter++; <br> 
 } 
 if (counter == 0){} <br> 
 else <br> 
 { 
 if (counter == 1) <br> 
 { 
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br> 
 cin>>pos; <br> 
 s = start; <br> 
 if (pos == 1) <br> 
 { 
 cout<<"Enter the new node : "; <br> 
 cin>>value; <br> 
 start->info = value; <br> 
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br> 
 } 
 else <br> 
 cout<<"Position out of range...!!!"<<endl; <br> 
 } 
 else <br> 
 { 
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br> 
 cin>>pos; <br> 
 s = start; <br> 
 if (pos == 1) <br> 
 { 
 cout<<"Enter the new node : "; <br> 
 cin>>value; <br> 
 start->info = value; <br> 
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br> 
 } 
 else if (pos > 1 && pos <= counter) <br> 
 { 
 cout<<"Enter the new node : "; <br> 
 cin>>value; <br> 
 for (i = 1; i < pos ; i++) <br> 
 { 
 s = s->next; <br> 
 } 
 s->info = value; <br> 
 cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl; <br> 
 } 
 else <br> 
 cout<<"Position out of range...!!!"<<endl; <br> 
 } 
 } 
} 
void single_llist::sort() <br> 
{ 
 struct node *ptr, *s; <br> 
 int value; <br> 
 if (start == NULL){} <br> 
 else <br> 
 { <br> 
 ptr = start; <br> 
 while (ptr != NULL) <br> 
 { <br> 
 for (s = ptr->next;s !=NULL;s = s->next) <br> 
 { <br> 
 if (ptr->info > s->info) <br> 
 { 
 value = ptr->info; <br> 
 ptr->info = s->info; <br> 
 s->info = value; <br> 
 } <br> 
 } <br> 
 ptr = ptr->next; <br> 
 } <br> 
 } <br> 
} <br> 
void single_llist::reverse() <br> 
{ <br> 
 struct node *ptr, *s; <br> 
 int value; <br> 
 if (start == NULL){} <br> 
 else <br> 
 { <br> 
 ptr = start; <br> 
 while (ptr != NULL) <br> 
 { <br> 
 for (s = ptr->next;s !=NULL;s = s->next) <br> 
 { <br> 
 if (ptr->info < s->info) <br> 
 { <br> <br> 
 value = ptr->info; <br> 
 ptr->info = s->info; <br> 
 s->info = value; <br> 
 } <br> 
 } <br> 
 ptr = ptr->next; <br> 
 } <br> 
 } <br> 
} <br> 
void single_llist::search() <br> 
{ <br> 
 int value, loc = 0, pos = 0, counter = 0; <br> 
 struct node *s; <br> 
 s = start; <br> 
 while (s != NULL) <br> 
 { <br> 
 s = s->next; <br> 
 counter++; <br> 
 } 
 if (start == NULL){} <br> 
 else <br> 
 { 
 cout<<"Enter the value to be searched : "; <br> 
 cin>>value;<br>  
 struct node *s; <br> 
 s = start; <br> 
 while (s != NULL) <br> 
 { <br> 
 pos++; <br> 
 if (s->info == value) <br> 
 { <br> 
 loc++; <br> 
 if(loc == 1) <br> 
 cout<<"Element "<<value<<" is found at position "<<pos; <br> 
 else if(loc <= counter) <br> 
 cout<<" , "<<pos; <br> 
 } <br> 
 s = s->next; <br> 
 } <br> 
 cout<<endl; <br> 
 if (loc == 0) <br> 
 cout<<"Element "<<value<<" not found in the list"<<endl; <br> 
 } <br> 
} <br> 
void single_llist::display() <br> 
{ <br> 
 struct node *temp; <br> 
 if (start == NULL) <br> 
 cout<<"Linked list is empty...!!!"<<endl; <br> 
 else <br> 
 { <br> 
 cout<<"Linked list contains : "; <br> 
 temp = start; <br> 
 while (temp != NULL) <br> 
 { <br> 
 cout<<temp->info<<" "; <br> 
 temp = temp->next; <br> 
 } <br> 
 cout<<endl; <br> 
 } <br> 
}<br> 

  
  OUTPUT
  ![image](https://user-images.githubusercontent.com/97940767/154895501-7b540fe7-6c6c-4692-8e7a-bfc6c29bc750.png)
   ![image](https://user-images.githubusercontent.com/97940767/154895572-4fbbeec1-4d99-4f6b-a27e-519eaee08115.png)
![image](https://user-images.githubusercontent.com/97940767/154895656-ad1a9e29-e578-4b8b-8e57-6360648973f6.png)
![image](https://user-images.githubusercontent.com/97940767/154895711-b1e8b726-3aac-41c5-b2b3-1aa1ea1c5e9c.png)
![image](https://user-images.githubusercontent.com/97940767/154895741-cebc2c32-af5b-40f7-a9b5-00aedcc610dc.png)
![image](https://user-images.githubusercontent.com/97940767/154895800-315ecb3f-7cfa-455c-99f1-9f4ab9dfcb80.png)
![image](https://user-images.githubusercontent.com/97940767/154895871-a2c2c268-8025-44d3-94e4-a290a9f347b9.png)
![image](https://user-images.githubusercontent.com/97940767/154895917-d036f56c-7e89-4afe-801d-4adcb84b075f.png)
 
 
 
 
**2. C++ PROGRAM TO SPLIT GIVEN LINKLIST INTO TWO IN SUCH A WAY THAT THE GIVEN ELEMENT 'ELE' MUST BE THE 1ST NODE OF 2ND LINKEDLIST**
 

#include<iostream>
using namespace std;<br>
struct Node{<br>
int value;<br>
struct Node *next;<br>
};<br>
struct Node* head = NULL;<br>
struct Node* sHead = NULL;<br>
struct Node* temp = NULL;<br>
void insert(int new_data){<br>
struct Node* new_node = new Node(); //(struct Node*)malloc(sizeof(struct Node));<br>
new_node->value = new_data;<br>
new_node->next = head;<br>
head = new_node;<br>
}<br>
int n;<br>
int ele;<br>
int splitIndex;<br>
int main(){<br>
int i;<br>
cout<<"Enter number of elements you want in the list\t";<br>
cin>>n;<br>
cout<<"Enter elements :" <<endl;<br>
for(i=0;i<n;i++){<br>
cin>>ele;<br>
insert(ele);<br>
}<br>
cout<<"\nList of elements : "<<endl;<br>
Node *t;<br>
t = head;<br>
while(t != NULL){<br>
cout<<t->value<<"\t";<br>
t = t->next;<br>
}<br>
cout<<"\n\nEnter the position you want the list to split ";<br>
cin>>splitIndex;<br>
while(splitIndex < 0 || splitIndex > n-1){<br>
cout<<"Invalid position. Try again."<<endl;<br>
cin>>splitIndex;<br>
}<br>
temp = head;<br>
for(i=0;i<=splitIndex;i++){<br>
if(i==splitIndex-1){<br>
Node *tN;<br>
tN = temp->next;<br>
sHead = tN;<br>
temp->next = NULL;<br>
break;<br>
}<br>
temp = temp->next;<br>
}<br>
temp = head;<br>
if(temp == NULL){<br>
cout<<"\nFirst list is empty"<<endl;<br>
}else{<br>
cout<<"\n\nFirst list element "<<endl;<br>
while(temp != NULL){<br>
cout<<temp->value<<"\t";<br>
temp = temp->next;<br>
}<br>
}<br>
temp = sHead;<br>
if(temp == NULL){<br>
cout<<"\nSecond list is empty"<<endl;<br>
}else{<br>
cout<<"\n\nSecond list elements "<<endl;<br>
while(temp != NULL){<br>
cout<<temp->value<<"\t";<br>
temp = temp->next;<br>
}<br>
}<br>
return 0;<br>
}<br>
OUTPUT:


 ![image](https://user-images.githubusercontent.com/97940767/154896537-afc6c835-1941-44a6-be99-596525cb3525.png)



**3. PROGRAM TO IMPLEMENT ADDITION OF TWO ARRAY**
 
 #include<iostream>
using namespace std;<br>

int main()<br>
{<br>
	int size, i, arr1[10], arr2[10], add[10];<br>
	
	cout << "\nPlease Enter the Array Size =  ";<br>
	cin >> size;<br>
	
	cout << "\nPlease Enter the First Array Items =  ";<br>
	for(i = 0; i < size; i++)<br>
	{<br>
		cin >> arr1[i];<br>
	}	<br>
	cout << "\nPlease Enter the Second Array Items =  ";<br>
	for(i = 0; i < size; i++)<br>
	{<br>
		cin >> arr2[i];<br>
	}<br>
	for(i = 0; i < size; i++)<br>
	{<br>
		add[i] = arr1[i] + arr2[i];<br>
		cout << arr1[i] << " + " << arr2[i] << " = " << add[i] << "\n";<br>
	}<br>
	cout << "\nThe Final Result of adding 2 One Dimensional Arrays = ";<br>
	for(i = 0; i < size; i++)<br>
	{<br>
		cout << add[i] << " ";<br>
	}<br>

 	return 0;<br>
}<br>

 
OUTPUT:
	
![image](https://user-images.githubusercontent.com/97940767/154901193-8ba9ae83-5b96-43f6-b9c1-eaf248aba9ba.png)

	
	
**4.C++ PROGRAM TO IMPLEMENT REVERSE ORDER OF ARRAY ELEMENT**
	
	#include<iostream>
using namespace std;<br>
int main()<br>
{<br>
    int arr[10], i;<br>
    cout<<"Enter 10 Array Elements: ";<br>
    for(i=0; i<10; i++)<br>
        cin>>arr[i];<br>
    cout<<"\nThe Original Array is:\n";<br>
    for(i=0; i<10; i++)<br>
        cout<<arr[i]<<" ";<br>
    cout<<"\n\nThe Reverse of Given Array is:\n";<br>
    for(i=(10-1); i>=0; i--)<br>
        cout<<arr[i]<<" ";<br>
    cout<<endl;<br>
    return 0;<br>
}<br>

OUTPUT:	
	
![image](https://user-images.githubusercontent.com/97940767/154901732-a6dce0f1-5b23-43f3-88a3-f0721c2c03ba.png)
	
	
**5. c++ PROGRAM TO STACK USNG ARRAY**
	
	#include <iostream>
using namespace std;<br>
int stack[100], n=100, top=-1;<br>
void push(int val) {<br>
   if(top>=n-1)<br>
   cout<<"Stack Overflow"<<endl;<br>
   else {<br>
      top++;<br>
      stack[top]=val;<br>
   }<br>
}<br>
void pop() {<br>
   if(top<=-1)<br>
   cout<<"Stack Underflow"<<endl;<br>
   else {<br>
      cout<<"The popped element is "<< stack[top] <<endl;<br>
      top--;<br>
   }<br>
}<br>
void display() {<br><br>
   if(top>=0) {<br>
      cout<<"Stack elements are:";<br>
      for(int i=top; i>=0; i--)<br>
      cout<<stack[i]<<" ";<br>
      cout<<endl;<br>
   } else<br>
   cout<<"Stack is empty";<br>
}<br>
int main() {<br>
   int ch, val;<br>
   cout<<"1) Push in stack"<<endl;<br>
   cout<<"2) Pop from stack"<<endl;<br>
   cout<<"3) Display stack"<<endl;<br>
   cout<<"4) Exit"<<endl;<br>
   do {<br>
      cout<<"Enter choice: "<<endl;<br>
      cin>>ch;<br>
      switch(ch) {<br>
         case 1: {<br>
            cout<<"Enter value to be pushed:"<<endl;<br>
            cin>>val;<br>
            push(val);<br>
            break;<br>
         }<br>
         case 2: {<br>
            pop();<br>
            break;<br>
         }
         case 3: {<br>
            display();<br>
            break;<br>
         }
         case 4: {<br>
            cout<<"Exit"<<endl;<br><br>
            break;<br>
         }
         default: {<br>
            cout<<"Invalid Choice"<<endl;<br>
         }<br>
      }<br>
   }while(ch!=4);<br>
   return 0;<br>
}<br>
	
**OUTPUT:	**
	
![image](https://user-images.githubusercontent.com/97940767/154904508-7693d04c-f8f7-42e3-ad11-272a060c5e4b.png)
	
	
**6. C++ PROGRAM TO IMPLEMENT THE BINARY SEARCH**
	
	#include<iostream>
using namespace std;<br>
int main()<br>
{<br>
    int i, arr[10], num, first, last, middle;<br>
    cout<<"Enter 10 Elements (in ascending order): ";<br>
    for(i=0; i<10; i++)<br>
        cin>>arr[i];<br>
    cout<<"\nEnter Element to be Search: ";<br>
    cin>>num;<br>
    first = 0;<br>
    last = 9;<br>
    middle = (first+last)/2;<br>
    while(first <= last)<br>
    {<br>
        if(arr[middle]<num)<br>
            first = middle+1;<br>
        else if(arr[middle]==num)<br>
        {<br>
            cout<<"\nThe number, "<<num<<" found at Position "<<middle+1;<br><br>
            break;<br>
        }<br>
        else<br>
            last = middle-1;<br>
        middle = (first+last)/2;<br>
    }<br>
    if(first>last)<br>
        cout<<"\nThe number, "<<num<<" is not found in given Array";<br>
    cout<<endl;<br>
    return 0;<br>
}<br>
	
	
**OUTPUT:	**
	
![image](https://user-images.githubusercontent.com/97940767/154905389-b94b32ef-f013-40d0-8500-a4f18c502d49.png)
	
	** 7. Construct a binary search tree (BST) to support the following operations. 
Given a key, perform a search in the BST. If the key is found then display “key found”.
i.	Insert an element into a binary search tree.
ii.	Delete an element from a binary search tree.
   Display the tree using inorder, preorder and post order traversal methods(a). **
	
	

# include <iostream> 
# include <cstdlib> 
using namespace std; <br>
struct node  <br>
{  <br>
 int info;  <br>
 struct node *left;  <br>
 struct node *right;  <br>
}*root;  <br>
class BST  <br>
{  <br>
 public:  <br>
 void find(int, node **, node **);  <br>
 void insert(node *, node *);  <br>
 void del(int);  <br>
 void case_a(node *,node *);  <br>
 void case_b(node *,node *);  <br>
 void case_c(node *,node *);  <br>
 void preorder(node *);  <br>
 void inorder(node *);  <br>
 void postorder(node *);  <br>
 void display(node *, int);  <br>
 BST()  <br>
 {  <br>
 root = NULL;  <br>
 }  <br>
};  <br>
int main()  <br>
{  <br>
 int choice, num;  <br>
 BST bst;  <br>
 node *temp;  <br>
 while (1)  <br>
 {  <br>
 cout<<"-----------------"<<endl;  <br>
 cout<<"Operations on BST"<<endl;  <br>
 cout<<"-----------------"<<endl;  <br>
 cout<<"1.Insert Element "<<endl;  <br>
 cout<<"2.Delete Element "<<endl;  <br>
 cout<<"3.Inorder Traversal"<<endl;  <br>
 cout<<"4.Preorder Traversal"<<endl;  <br>
 cout<<"5.Postorder Traversal"<<endl;  <br>
 cout<<"6.Display"<<endl;  <br>
 cout<<"7.Quit"<<endl;  <br>
 cout<<"Enter your choice : ";  <br>
 cin>>choice;  <br>
 switch(choice)  <br>
 {  <br>
 case 1:  <br>
 temp = new node;  <br>
 cout<<"Enter the number to be inserted : ";  <br>
 cin>>temp->info;  <br>
 bst.insert(root, temp); <br> 
 break;  <br>
 case 2:  <br>
 if (root == NULL)  <br>
 {  <br>
 cout<<"Tree is empty, nothing to delete"<<endl;  <br>
 continue;  <br>
 }  <br>
 cout<<"Enter the number to be deleted : ";  <br>
 cin>>num;  <br>
 bst.del(num);  <br>
 break;  <br>
 case 3:  <br>
 cout<<"Inorder Traversal of BST:"<<endl;  <br>
 bst.inorder(root);  <br>
 cout<<endl;  <br>
 break;  <br>
 case 4:  <br>
 cout<<"Preorder Traversal of BST:"<<endl;  <br>
 bst.preorder(root);  <br>
 cout<<endl;  <br>
 break;  <br>
 case 5:  <br>
 cout<<"Postorder Traversal of BST:"<<endl;  <br>
 bst.postorder(root);  <br>
 cout<<endl;  <br>
 break;  <br>
 case 6:  <br>
 cout<<"Display BST:"<<endl;  <br>
 bst.display(root,1);  <br>
 cout<<endl;  <br>
 break;  <br>
 case 7:  <br>
 exit(1);  <br>
 default:  <br>
 cout<<"Wrong choice"<<endl;  <br>
 }  <br>
 }  <br>
}  <br>
void BST::find(int item, node **par, node **loc)  <br>
{  <br> 
 node *ptr, *ptrsave;   <br>
 if (root == NULL) <br> 
 {  <br>
 *loc = NULL;  <br>
 *par = NULL;  <br>
 return;  <br>
 }  <br> 
 if (item == root->info)  <br>
 {  <br>
 *loc = root;  <br>
 *par = NULL;  <br>
 return;  <br>
 } 
 if (item < root->info)  <br>
 ptr = root->left;  <br>
 else  <br>
 ptr = root->right;  <br>
 ptrsave = root;  <br>
 while (ptr != NULL)  <br>
 {  <br>
 if (item == ptr->info)  <br>
 {  <br>
 *loc = ptr;  <br>
 *par = ptrsave;  <br>
 return;  <br>
 }  <br>
 ptrsave = ptr;  <br>
 if (item < ptr->info)  <br>
 ptr = ptr->left;  <br>
 else  <br>
 ptr = ptr->right;  <br>
 }  <br>
 *loc = NULL;  <br>
 *par = ptrsave;  <br>
}  <br>

void BST::insert(node *tree, node *newnode)  <br>
{  <br>
 if (root == NULL)  <br>
 {  <br>
 root = new node;  <br> 
 root->info = newnode->info;   <br>
 root->left = NULL;  <br>
 root->right = NULL;  <br>
 cout<<"Root Node is Added"<<endl;  <br>
 return;  <br>
 }  <br>
 if (tree->info == newnode->info)  <br>
 {  <br>
 cout<<"Element already in the tree"<<endl;  <br>
 return;  <br>
 }  <br>
 if (tree->info > newnode->info)  <br>
 {  <br>
 if (tree->left != NULL)  <br>
 {  <br>
 insert(tree->left, newnode);  <br>
 }  <br>
 else  <br>
 {  <br>
 tree->left = newnode;  <br>
 (tree->left)->left = NULL;  <br>
 (tree->left)->right = NULL;  <br>
 cout<<"Node Added To Left"<<endl;  <br>
 return;  <br> 
 }   <br>
 }  <br>
 else  <br>
 {  <br>
 if (tree->right != NULL)  <br>
 {  <br>
 insert(tree->right, newnode);  <br>
 }  <br>
 else  <br>
 {  <br>
 tree->right = newnode;  <br>
 (tree->right)->left = NULL;  <br>
 (tree->right)->right = NULL;  <br>
 cout<<"Node Added To Right"<<endl;  <br>
 return;  <br>
 }  <br>
 }  <br>
}  <br>

void BST::del(int item)  <br>
{  <br>
 node *parent, *location;  <br>
 if (root == NULL)  <br>
 {  <br>
 cout<<"Tree empty"<<endl;  <br>
 return;  <br>
 }  <br>
 find(item, &parent, &location);  <br>
 if (location == NULL)  <br>
 {  <br>
 cout<<"Item not present in tree"<<endl;  <br> <br>
 return;  <br>
 }  <br>
 if (location->left == NULL && location->right == NULL)  <br>
 case_a(parent, location);  <br>
 if (location->left != NULL && location->right == NULL)  <br>
 case_b(parent, location);  <br>
 if (location->left == NULL && location->right != NULL)  <br>
 case_b(parent, location);  <br>
 if (location->left != NULL && location->right != NULL)  <br> 
 case_c(parent, location);  <br>
 free(location);  <br>
}  <br>
 

void BST::case_a(node *par, node *loc )  <br>
{  <br> 
 if (par == NULL)   <br>
 {  <br>
 root = NULL;  <br>
 }  <br>
 else  <br>
 {  <br>
 if (loc == par->left)  <br>
 par->left = NULL;  <br>
 else  <br>
 par->right = NULL;  <br> 
 }   <br>
}  <br>
 

void BST::case_b(node *par, node *loc)  <br>
{  <br>
 node *child;  <br>
 if (loc->left != NULL)  <br>
 child = loc->left;  <br>
 else  <br>
 child = loc->right;  <br>
 if (par == NULL)  <br>
 {  <br>
 root = child;  <br>
 }  <br>
 else  <br>
 {  <br>
 if (loc == par->left)  <br>
 par->left = child;  <br>
 else  <br>
 par->right = child;  <br>
 }  <br>
}  <br>
 

void BST::case_c(node *par, node *loc)  <br>
{  <br>
 node *ptr, *ptrsave, *suc, *parsuc;  <br>
 ptrsave = loc;  <br>
 ptr = loc->right;  <br>
 while (ptr->left != NULL)  <br>
 {  <br>
 ptrsave = ptr;  <br>
 ptr = ptr->left;  <br>
 }  <br>  
 suc = ptr;    <br>
 parsuc = ptrsave;  <br>
 if (suc->left == NULL && suc->right == NULL)  <br>
 case_a(parsuc, suc);  <br>
 else  <br>
 case_b(parsuc, suc);  <br>
 if (par == NULL)  <br>
 {  <br> 
 root = suc;  <br>
 }  <br>
 else  <br>
 {  <br>
 if (loc == par->left)  <br>
 par->left = suc;  <br>
 else  <br>
 par->right = suc;  <br>
 }  <br>
 suc->left = loc->left;  <br>
 suc->right = loc->right;  <br>
}  <br>
 
 
void BST::preorder(node *ptr)  <br>
{  <br>
 if (root == NULL)  <br>
 {  <br>
 cout<<"Tree is empty"<<endl;  <br>
 return;  <br> <br>
 }  <br>
 if (ptr != NULL)  <br>
 {  <br>
 cout<<ptr->info<<" ";  <br> <br>
 preorder(ptr->left);  <br>
 preorder(ptr->right);  <br>
 }  <br>
}  <br>

void BST::inorder(node *ptr)  <br>
{  <br>
 if (root == NULL)  <br>
 {  <br>
 cout<<"Tree is empty"<<endl; <br> 
 return;  <br>
 }  <br>
 if (ptr != NULL)  <br>
 {  <br>
 inorder(ptr->left);  <br>
 cout<<ptr->info<<" ";  <br>
 inorder(ptr->right); <br> 
 }  <br>
}  <br>
 
void BST::postorder(node *ptr)  <br>
{  <br>
 if (root == NULL)  <br>
 {  <br>
 cout<<"Tree is empty"<<endl;  <br>
 return;  <br>
 }  <br>
 if (ptr != NULL) <br> 
 {  <br>
 postorder(ptr->left);  <br>
 postorder(ptr->right);  <br>
 cout<<ptr->info<<" ";  <br>
 }  <br>
}  <br>
 
void BST::display(node *ptr, int level)  <br>
{  <br>
 int i;  <br>
 if (ptr != NULL)  <br>
 {  <br>
 display(ptr->right, level+1);  <br>
 cout<<endl;  <br>
 if (ptr == root)  <br>
 cout<<"Root->: ";  <br>
 else  <br>
 { 
 for (i = 0;i < level;i++)  <br>
 cout<<" ";  <br>
 }  <br>
 cout<<ptr->info;  <br>
 display(ptr->left, level+1);  <br>
 }  <br>
} <br>


![image](https://user-images.githubusercontent.com/97940767/155078630-74dbaf58-690f-4abc-b860-05333ccf3f1e.png)
![image](https://user-images.githubusercontent.com/97940767/155078870-ee1487df-d42c-49c2-9ecc-e63ce6537037.png)
![image](https://user-images.githubusercontent.com/97940767/155078964-1d95a8d8-7dec-4fee-9608-42e21ef4e4ba.png)
![image](https://user-images.githubusercontent.com/97940767/155079002-150a48c9-37bd-43b6-a05f-b998e7668527.png)





	
	
	











