# ReverseList
import java.util.*;
class Node {
    int data;
    Node next;
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}
class SingleLinkedlist{
    Node head;
    public void insert(int data){
        Node newnode=new Node(data);
        if(head==null){
            head=newnode;
            
        }
        else{
            Node temp=head;
            while(temp.next!=null){
            temp=temp.next;
            }
            temp.next=newnode;
        }
    }
    public void reverse(){
        Node before=null;
        Node current=head;
        Node after=null;
        while(current!=null){
            after=current.next;
            current.next=before;
            before=current;
            current=after;
        }
        head=before;
    }
    public void display(){
        Node temp=head;
        while(temp!=null){
            System.out.println(" "+temp.data);
            temp=temp.next;
        }
    }
}
class Main
{
	public static void main(String[] args) 
	{
	    Scanner sc=new Scanner(System.in);
	   // SingleLinkedlist list=new SingleLinkedlist();
	    int t=sc.nextInt();
	    for(int i=1;i<=t;i++){
	        SingleLinkedlist list=new SingleLinkedlist();
	        int n=sc.nextInt();
	        for(int j=0;j<n;j++){
	            int data=sc.nextInt();
	            list.insert(data);
	        }
	        list.reverse();
	        list.display();
	    }
	}
}
