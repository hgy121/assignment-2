# 구현 과제

## 스택
```
#include <stdio.h>
#include <string.h>
int push();
int pop();
int stack[100];
int len = 0;

int main() {
    char a[5];
    while(1){
        printf("push / pop / stop : ");
        scanf("%s",a);
        printf("\n");
        if(!strcmp(a,"push")) push();
        else if(!strcmp(a,"pop")) pop();
        else if(!strcmp(a,"stop")) break;
        else{
            printf("This is not the correct format.\n");
            printf("Please enter again.\n");
        }
    }
    return 0;
}

int push(){
    if(len==100){
        printf("The space is full.\n");
        return 0;
    }
    int n;
    scanf("%d",&n);
    stack[len] = n;
    len++;
}

int pop(){
    if(len==0){
        printf("The space is empty.\n");
        return 0;
    }
    printf("%d\n",stack[len-1]);
    len--;
}
```

## 큐
```
#include <stdio.h>
#include <string.h>
int enqueue();
int dequeue();
int queue[100];
int len = 0;

int main() {
    char a[10];
    while(1){
        printf("enqueue / dequeue / stop : ");
        scanf("%s",a);
        printf("\n");
        if(!strcmp(a,"enqueue")) enqueue();
        else if(!strcmp(a,"dequeue")) dequeue();
        else if(!strcmp(a,"stop")) break;
        else{
            printf("This is not the correct format.\n");
            printf("Please enter again.\n");
        }
    }
    return 0;
}

int enqueue(){
    if(len==100){
        printf("The space is full.\n");
        return 0;
    }
    int n;
    scanf("%d",&n);
    queue[len] = n;
    len++;
}

int dequeue(){
    if(len==0){
        printf("The space is empty.\n");
        return 0;
    }
    printf("%d\n",queue[0]);
    for(int i=0;i<len;i++){
        queue[i] = queue[i+1];
    }
    len--;
}
```

## 백터
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *vector = NULL;
    int size = 0;

    for(int i=0;i<10;i++){
        size++;
        vector = realloc(vector,size*4);
        vector[size-1] = i;
    }

    for(int i=0;i<10;i++){
        printf("%d ",vector[i]);
    }
    return 0;
}
```

## 링크드리스트
```
#include <stdio.h>

struct node{
    int data;
    struct node* next;
};

int main() {
    struct node a,b,c;
    a.data = 100;
    a.next = &b;
    b.data = 200;
    b.next = &c;
    c.data = 300;
    c.next = NULL;
    return 0;
}
```
