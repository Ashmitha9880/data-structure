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
 
 
 
 
 C++ PROGRAM TO SPLIT GIVEN LINKLIST INTO TWO IN SUCH A WAY THAT THE GIVEN ELEMENT 'ELE' MUST BE THE 1ST NODE OF 2ND LINKEDLIST
 

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
	
	![image](https://user-images.githubusercontent.com/97940767/154900837-3aeeb512-e353-4a77-978c-5cbbca496ffc.png)










