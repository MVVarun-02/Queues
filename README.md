# Queues
Inserting Deleting elements from a Queue and Display them

#include<stdio.h>

#include<stdlib.h>

#define max 10


int q[10],front=0,rear= -1;

void main() {

  int ch;
  
  void insert();
  
  void delete();
  
  void display();
  
  printf("1.insert\n2.delete\n3.display\n0.exit\n");
  
  while(1) {
  
    printf("Enter your choice:");
    
    scanf("%d",&ch);
    
    switch(ch) {
    
      case 1:
      
        insert();
        
        break;
        
      case 2:
      
        delete();
        
        break;
        
      case 3:
      
        display();
        
        break;
        
      case 0:
      
        exit(1);
        
      default:
      
        printf("Invalid option\n");
        
    }
    
  }
  
}


void insert() {

  int x;
  
  if((front==0&&rear==max-1)||(front>0&&rear==front-1)) {
  
    printf("Queue is overflow\n");
    
  }
  
  else {
  
    printf("Enter element to be insert:");
    
    scanf("%d",&x);
    
  }
  
  if(rear==max-1&&front>0) {
  
    rear=0;
    
    q[rear]=x;
    
  }
  
  else {
  
    if((front==0&&rear==-1)||(rear!=front-1))
    
    q[++rear]=x;
    
  }
  
}


void delete() {

  int a;
  
  if((front==0)&&(rear==-1)) {
  
    printf("Queue is empty\n");
    
    exit(1);
    
  }
  
  if(front==rear) {
  
    a=q[front];
    
    rear=-1;
    
    front=0;
    
  }
  
  else if(front==max-1) {
  
    a=q[front];
    
    front=0;
    
  }
  
  else {
  
    a=q[front++];
    
    printf("Deleted element is:%d\n",a);
    
  }
  
}


void display() {

  int i,j;
  
  if(front==0&&rear==-1) {
  
    printf("Queue is empty\n");
    
    exit(1);
    
  }
  
  if(front>rear) {
  
    for(i=0;i<=rear;i++) {
    
      printf("\t%d",q[i]);
      
    }
    
    for(j=front;j<=max-1;j++) {
    
      printf("\t%d",q[j]);
      
    }
    
    printf("\nrear is at %d\n",q[rear]);
    
    printf("\nfront is at %d\n",q[front]);
    
  }
  
  else {
  
    for(i=front;i<=rear;i++) {
    
      printf("\t%d",q[i]);
      
    }
    
    printf("\nrear is at %d\n",q[rear]);
    
    printf("\nfront is at %d\n",q[front]);
    
  }
  
  printf("\n");
  
}
