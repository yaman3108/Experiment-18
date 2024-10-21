# Experiment 18



## Aim:
To study and implement Stack implementation using array


## Apparatus:
Vs Code, Github


## Theory:

A stack is a linear data structure that follows the Last In, First Out (LIFO) principle. This means that the last element added to the stack is the first one to be removed. In C++, stacks can be implemented using arrays or linked lists. In this program we wil use stack implementation using arrays.In stack implementation using array the stack is represented by an array stack[].

### Basic operations:
1: Push: Adds an element to the top of the stack.
   Before adding an element, check if the stack is full (top == max - 1), where max is the maximum capacity of the stack.
   If not full, increment top and insert the new element at stack[top].
   
2: Pop: Removes the element from the top of the stack.
        Before removing an element, check if the stack is empty (top == -1).
        If not empty, remove the element at stack[top] and decrement top.
        
3: Peek/Top: Returns the top element without removing it.
             Return the element at stack[top] without modifying top.
             Check if the stack is empty before accessing stack[top].


## Explanation:

### Class Definition (Stack):
A class named Stack encapsulates the stack operations and attributes.
An array arr[size] is used to store the stack elements.
An integer variable top keeps track of the index of the top element in the stack.

### Constructor (Stack()):
Initializes top to -1, indicating that the stack is initially empty.
Push Method (push(int value)):
Checks if the stack is full. If so, it displays an error message.
Otherwise, increments top and stores the value at arr[top].

### Pop Method (pop()):

Checks if the stack is empty. If so, it displays an error message.
Otherwise, it decrements top, effectively removing the top element.
### Peek Method (peek()):

Returns the value at arr[top] without removing it.
If the stack is empty, it returns an error value.

## Code:

### Stack using array: 
```
#include<iostream>
using namespace std;
#define size 5
#define ERROR -9999

class Stack{
    int top, ar[size];
    public:
    Stack(){
        top=-1;
        ar[0]=0;
    }
    void push(int);
    int pop();
    int peak();
    void disp();
};
void Stack::push(int num){
    if(top==size-1){
        cout<<"STACK OVERFLOW: Stack is full"<<endl;
        return;
    }
    else{
        ar[++top]=num;
    }
}
int Stack::pop(){
    int val;
    if(top==-1){
        cout<<"STACK UNDERFLOW: Stack is empty"<<endl;
        return ERROR;
    }
    else{
        val=ar[top--];
        return val;
    }
}
int Stack::peak(){
    if(top==-1){
        cout<<"STACK UNDERFLOW: Stack is empty"<<endl;
        return ERROR;
    }
    else{
        return ar[top];
    }
}
void Stack::disp(){
    if(top==-1){
        cout<<"STACK UNDERFLOW: Stack is empty"<<endl;
        return;
    }
    else{
        int i=0;
        while(i!=(top+1)){
            cout<<ar[i]<<"  ";
            i++;
        }

    }
}

int main(){
    Stack s1;
    s1.push(7);
    s1.push(10);
    s1.push(4);
    int val=s1.pop();
    cout<<val<<endl;
    int top=s1.peak();
    cout<<top<<endl;
    s1.disp();
    return 0;
}
```
### Output:
<img width="938" alt="Screenshot 2024-10-21 at 1 47 32 PM" src="https://github.com/user-attachments/assets/3682dc49-376e-46d8-8664-9f58856ad6d4">


## Conclusion:
This program helps us understand how stacks can be implemented using arrays. We learnt the different commands/keywords used in stacks such as push, pop and peek.
