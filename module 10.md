# EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.

## Aim:
To write a C program to search a given element in the given linked list.

## Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
## Program:

```c
struct Node{
    int data; 
    struct Node *next;
}*head;

void search(int data)
{
 
 struct Node*temp=head;
 int flag=0;
 int i=0;
 while(temp->data!=data)
 {
     i++;
     if(temp->next!=NULL)
     temp=temp->next;
     else break;
     
 }
 if(temp->data==data)
 {
     printf("item %d found at location %d",data,i+1);
     flag=1;
 }
 if(flag==0)
 {
     printf("Item not found");
 }
 
    
}

```

## Output:

<img width="794" height="528" alt="651984104-fbd416c6-99f4-49e9-9b8c-7064f0236314" src="https://github.com/user-attachments/assets/8a914cbd-c68b-4f2b-a7d1-fa48caeb05d3" />


## Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
# EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.

## Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
## Program:

```c
struct Node{
    int data; 
    struct Node *next;
}*head;


void insert(int data)
{
    struct Node* n=(struct Node*)malloc(sizeof(struct Node));
    struct Node* temp=head;
    n->data=data;
    n->next=NULL;
    if(head==NULL){
        
        head=n;
    }else{
        while(temp->next!=NULL){
            temp=temp->next;
        }
        temp->next=n;
        
    }
}

```

## Output:

<img width="382" height="526" alt="651984457-0f558cb6-7557-4ec9-a7b1-af72c2acd4c1" src="https://github.com/user-attachments/assets/c79c6da0-2bc1-4696-80ca-f23470387a26" />
 
## Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
# EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST

## Aim:
To write a C program to traverse a doubly linked list.

## Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
## Program:

```c
struct Node
{
    struct Node *prev;
    struct Node *next;
    int data;
}*head;

void display()
{
    struct Node* temp=head;
    while(temp!=NULL)
    {
        printf("%d\n",temp->data);
        temp=temp->next;
    }
    
}

```

## Output:

<img width="696" height="878" alt="651984775-40782081-91e4-4c30-901a-d2ee619843ac" src="https://github.com/user-attachments/assets/91f30040-ef82-4b00-b0fe-6d2c29fb3607" />


## Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



# EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST

## Aim:
To write a C program to insert an element in doubly linked list

## Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
## Program:

```c
struct Node
{
    struct Node *prev;
    struct Node *next;
    float data;
}*head;

void insert(float data)
{
    struct Node* n=(struct Node*)malloc(sizeof(struct Node));
    struct Node* temp=head;
    n->data=data;
    n->next=NULL;
    if(head==NULL){
        head=n;
        return;
    }
    while(temp->next!=NULL){
        temp=temp->next;
    }
    temp->next=n;
    
    
}


```

## Output:

<img width="429" height="472" alt="651985105-4784da6a-6c6e-4db6-8cff-af80dbceb82d" src="https://github.com/user-attachments/assets/3fd0ba93-8c66-4352-a6da-14f2b5afdb97" />


## Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




# EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




## Aim:
To write a C function that deletes a given element from a linked list.

## Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


## Program:

```c

struct Node
{
    int data; 
    struct Node *next;
}*head;
void display()
{
    struct Node* temp=head;
    while(temp!=NULL)
    {
        printf("%d ",temp->data);
        temp=temp->next;
    }
}
void insert(int data)
{
    struct Node* temp=head;
    struct Node* ptr=(struct Node*)malloc(sizeof(struct Node));
    ptr->data=data;
    ptr->next=NULL;
    if(head==NULL)
    {
        head=ptr;
    }else
    {
        while(temp->next!=NULL)        {
            temp=temp->next;
        }
        temp->next=ptr;
    }
}
void search(int data)
{
    int i=1;
    struct Node* temp=head;
    if(head==NULL)
    {
        printf("Elements not found");
    }else
    {
        while(temp!=NULL)
        {
            
            if(temp->data==data)
            {
                printf("item %d found at location %d\n",data,i);
                return;
            }
            i++;
            temp=temp->next;
        }
        printf("Item not found\n");
    }
}
void delete()
{
    struct Node* temp=head;
    if(head==NULL)
    {
        printf("UNDERFLOW");
    }else
    {
        head=head->next;
        free(temp);
        printf("Node deleted\n");
    }
    
}



```

## Output:

<img width="954" height="750" alt="651985380-c309cc25-9889-43fe-be31-1dbf57969162" src="https://github.com/user-attachments/assets/96e9df05-de8d-427a-92d4-da836c16d284" />


## Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





