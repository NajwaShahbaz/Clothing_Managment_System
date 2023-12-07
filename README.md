# Clothing_Managment_System
#include <iostream>
#include<windows.h>
using namespace std;
struct Node {
public:
    int Carid;
    string Carname;
    string Carcolor;
    string CarModel;
    int Carprice;
    
    Node* next;

    Node(int Carid,string Carname,string Carcolor,string CarModel,int Carprice) {
        this->Carid = Carid;
        this->Carname=Carname;
        this->Carcolor=Carcolor;
        this->CarModel=CarModel;
        this->Carprice=Carprice;
        this->next = NULL;
    }
};

class ShowRoom {
private:
    Node* head;

public:
    ShowRoom() {
        head = NULL;
    }

    void insertAtHead(int Carid,string Carname,string Carcolor,string CarModel,int Carprice) {
        Node* newNode = new Node(Carid,Carname,Carcolor,CarModel,Carprice);
        newNode->next = head;
        head = newNode;
    }

    void insertAtTail(int Carid,string Carname,string Carcolor,string CarModel,int Carprice) {
        Node* newNode = new Node(Carid,Carname,Carcolor,CarModel,Carprice);
        if (head == NULL) {
            head = newNode;
        } else {
            Node* temp = head;
            while (temp->next != NULL) {
                temp = temp->next;
            }
            temp->next = newNode;
        }
    }

    void deleteNode(int Carid) {
    if (head == NULL) {
        cout << "List is empty. Cannot delete node." << endl;
        return;
    }
    if (head->Carid == Carid) {
        Node* temp = head;
        head = head->next;
        delete temp;
        return;
    }

    Node* prev = NULL;
    Node* curr = head;

    while (curr != NULL && curr->Carid != Carid) {
        prev = curr;
        curr = curr->next;
    }
    if (curr != NULL) {
        prev->next = curr->next;
        delete curr;
    } else {
        cout << "Node not found in the list." << std::endl;
    }
}

int search(int Carid) {
    Node* temp = head;
    while (temp != NULL) {
        if (temp->Carid == Carid) {
            cout<<"\n***Founded***\n";
            return 1;
        }
        temp = temp->next;
    }
    cout<<"\n***Not Found***\n";
    return 0;  // Node not found
}
void update(int oldValue,int Carid,string Carname,string Carcolor,string CarModel,int Carprice) {
    Node* temp = head;
    while (temp != NULL) {
        if (temp->Carid == oldValue) {
            temp->Carname = Carname;  
            temp->Carcolor=Carcolor;
            temp->CarModel=CarModel;
            temp->Carprice=Carprice;
            return;
        }
        temp = temp->next;
    }
    cout << "Node with old value not found in the list." << endl;
}

    void display() {
        Node* temp = head;
        while (temp != NULL) {
            cout<<"Car ID: " << temp->Carid << " -> ";
            cout<<"Car Name: "<<temp->Carname<<"->";
            cout<<"Car Price: "<<temp->Carprice<<"->";
            cout<<"Car Color: "<<temp->Carcolor<<"->";
            cout<<"Car Model: "<<temp->CarModel<<"\n";
            temp = temp->next;
        }
        cout << "NULL" <<endl;
    }
};
struct Node2 {
public:
    int id;
    string name;
    int age;
    string gender;
    int salary;
    
    Node2* next;

    Node2(int id,string name,int age,string gender,int salary) {
        this->id = id;
        this->name=name;
        this->age=age;
        this->gender=gender;
        this->salary=salary;
        this->next = NULL;
    }
};
class Admin {
private:
    Node2* head;

public:
    Admin() {
        head = NULL;
    }

    void InsertAtHead(int id,string name,int age,string gender,int salary) {
        Node2* newNode = new Node2(id,name,age,gender,salary);
        newNode->next = head;
        head = newNode;
    }

    void InsertAtTail(int id,string name,int age,string gender,int salary) {
        Node2* newNode = new Node2(id,name,age,gender,salary);
        if (head == NULL) {
            head = newNode;
        } else {
            Node2* temp = head;
            while (temp->next != NULL) {
                temp = temp->next;
            }
            temp->next = newNode;
        }
    }
    
      void DeleteNode(int id) {
    if (head == NULL) {
        cout << "List is empty. Cannot delete node." << std::endl;
        return;
    }
    if (head->id == id) {
        Node2* temp = head;
        head = head->next;
        delete temp;
        return;
    }

    Node2* prev = NULL;
    Node2* curr = head;

    while (curr != NULL && curr->id != id) {
        prev = curr;
        curr = curr->next;
    }
    if (curr != NULL) {
        prev->next = curr->next;
        delete curr;
    } else {
        cout << "Node not found in the list." << std::endl;
    }
}
int  Search(int id) {
    Node2* temp = head;
    while (temp != NULL) {
        if (temp->id == id) {
            cout<<"\n^^^Founded^^^\n";
            return 0;
        }
        temp = temp->next;
    }
    cout<<"\n^^^Not Found^^^\n";
    return NULL;  
}
void Update(int oldValue, int id,string name,int age,string gender,int salary) {
    Node2* temp = head;
    while (temp != NULL) {
        if (temp->id == oldValue) {
            temp->name = name;
			temp->age=age;
			temp->gender=gender;
			temp->salary=salary;
            return;
        }
        temp = temp->next;
    }
    cout << "Node with old value not found in the list." << endl;
}

    void Display() {
        Node2* temp = head;
        while (temp != NULL) {
            cout<<"StaffID: "<< temp->id << " -> ";
            cout<<"Name: "<<temp->name <<"->";
			cout<<"Age: "<<temp->age<<"->";
			cout<<"Gender: "<<temp->gender<<"->";
			cout<<"Salary: "<<temp->salary<<"\n";
			   temp = temp->next;
        }
        cout << "NULL" <<endl;
    }
};
struct Node3{
	public:
    string name;
    int id;
    int days;
    
    Node3* next;

    Node3(int id,string name,int days) {
        this->id = id;
        this->name=name;
        this->days=days;
        this->next = NULL;
    }
};
class Buyyer {
private:
    Node3* head;

public:
    Buyyer() {
        head = NULL;
    }

    void InsertAtHead(int id,string name,int days) {
        Node3* newNode = new Node3(id,name,days);
        newNode->next = head;
        head = newNode;
    }
    
    void Display() {
        Node3* temp = head;
        while (temp != NULL) {
            cout<<"ID: "<< temp->id << " -> ";
            cout<<"Car Name: "<<temp->name <<"\n";
			   temp = temp->next;
        }
        cout << "NULL" <<endl;
    }
};
int strt()
{
	Sleep(200);
	Sleep(200);
	cout<<"\t\t\t\t                 ______________              "<<endl;
	Sleep(200);
	cout<<"\t\t\t\t                 |             |             "<<endl;
	Sleep(200);
	cout<<"\t\t\t\t                 |             |             "<<endl;
	Sleep(200);
	cout<<"\t\t\t\t                 |             |             "<<endl;
	Sleep(200);
	cout<<"\t\t\t\t_________________|             |___________________"<<endl;
	Sleep(200);
	cout<<"\t\t\t\t|                                                  |"<<endl;
	Sleep(200);
	cout<<"\t\t\t\t|                                                  |"<<endl;
	Sleep(200);
	cout<<"\t\t\t\t|                                                  |"<<endl;
	Sleep(200);
	cout<<"\t\t\t\t|              Welcome to car Rental               |"<<endl;
	Sleep(200);
	cout<<"\t\t\t\t|                Managment System                  |"<<endl;
	Sleep(200);
	cout<<"\t\t\t\t|                                                  |"<<endl;
	Sleep(200);
	cout<<"\t\t\t\t|                                                  |"<<endl;
	Sleep(200);
	cout<<"\t\t\t\t|       ________             ________              |"<<endl;
	Sleep(200);
	cout<<"\t\t\t\t|_______|       |____________|       |_____________|"<<endl;
	Sleep(200);
	cout<<"\t\t\t\t        |       |            |       |       "<<endl;
	Sleep(200);
	cout<<"\t\t\t\t        |       |            |       |       "<<endl;
	Sleep(200);
	cout<<"\t\t\t\t        |_______|            |_______|       "<<endl;
	Sleep(200);
	
	cout<<"\n\n\t\t\t\t\t%%%%CAR MANAGMENT SYSTEM%%%%"<<endl;
	Sleep(800);
}

int main() {
	strt();
ShowRoom i;
int stop=1;
int choice,ch;
while(1)
{
	system("color 70");
	system("cls");
cout<<"\n\nEnter any number As:\n1-Car ShowRoom\n2-Admin\n3-Rent a Car\n4-Exit\n\n";
cin>>choice;
switch(choice)
{
	case 1:
		{
				
			while(stop!=0)
			{
			system("color 0F");
			cout<<"\n******Car ShowRoom********\n";
			cout<<"Enter choice\n1-ADD Car\n2-Delete Car\n3-Update Car\n4-Search Car\n5-View Car\n6-Exit\n";
			cin>>ch;
			switch(ch)
			{
				case 1:
					{
						system("color 0E");
						int id,p;
						string n,c,m;
						cout<<"Enter ID: ";
						cin>>id;
						cout<<"Enter Name: ";
						cin>>n;
						cout<<"Enter Color: ";
						cin>>c;
						cout<<"Enter Model: ";
						cin>>m;
						cout<<"Enter Price: ";
						cin>>p;
						i.insertAtHead(id,n,c,m,p);
						cout<<"\nCar Added Sucessfully\n";
							break;
					}
				case 2:
					{
						system("color 0A");
						int id;
						cout<<"Enter Id To Delete Car";
						cin>>id;
						i.deleteNode(id);
						cout<<"\nCar Deleted Sucessfully\n";	
							break;
					}
				case 3:
					{
						system("color 07");
						string n,c,m;
						int id,p;
						cout<<"Enter Id To Update Cars";
						cin>>id;
						cout<<"Enter Name: ";
						cin>>n;
						cout<<"Enter Color: ";
						cin>>c;
						cout<<"Enter Model: ";
						cin>>m;
						cout<<"Enter Price: ";
						cin>>p;
						i.update(id,id,n,c,m,p);
						cout<<"\nUpdated Sucessfully\n";
							break;
					}
				case 4:
					{
						system("color 0B");
						int id;
						cout<<"Enter Id To Search Car";
						cin>>id;
						i.search(id);
						cout<<"\nSearched\n";
							break;
					}
				case 5:
					{
						system("color 09");
						i.display();
						cout<<"\n**View**\n";
						break;
					}
				case 6:
					{
						stop=0;
						cout<<"\n\n****\n\n";
					}
			}
		}
		break;
		}
	case 2:
		{
			Admin y;
			cout<<"\n******Admin********\n";
			stop=1;
			while(stop!=0)
			{
			cout<<"\n******Admin********\n";
			cout<<"Enter choice\n1-ADD Staff\n2-Delete Staff\n3-Update Staff\n4-Search Staff\n5-View Staff\n6-Exit\n";
			cin>>ch;
			switch(ch)
			{
				case 1:
					{
						
						system("color 0E");
						int id,salary,a;
						string n,g;
						cout<<"Enter ID: ";
						cin>>id;
						cout<<"Enter Name: ";
						cin>>n;
						cout<<"Enter age: ";
						cin>>a;
						cout<<"Enter Gender: ";
						cin>>g;
						cout<<"Enter Salary: ";
						cin>>salary;
					
						y.InsertAtHead(id,n,a,g,salary);
						cout<<"\nStaff Added Sucessfully\n";
							break;
					}
				case 2:
					{
						system("color 0A");
						int id;
						cout<<"Enter Id To Delete Staff Member";
						cin>>id;
						y.DeleteNode(id);
						cout<<"\nStaff Member Deleted Sucessfully\n";	
							break;
					}
				case 3:
					{
						system("color 07");
						string n,g;
						int id,s,a;
						cout<<"Enter Id To Update Staff Member";
						cin>>id;
						cout<<"Enter Name: ";
						cin>>n;
						cout<<"Enter Age: ";
						cin>>a;
						cout<<"Enter Gender: ";
						cin>>g;
						cout<<"Enter Salary: ";
						cin>>s;
						y.Update(id,id,n,a,g,s);
						cout<<"\nUpdated Sucessfully\n";
							break;
					}
				case 4:
					{
						system("color 0B");
						int id;
						cout<<"Enter Id To Delete Staff Member";
						cin>>id;
						y.Search(id);
						cout<<"\nSearched\n";
							break;
					}
				case 5:
					{
						system("color 09");
						y.Display();
						cout<<"\n^^All Staffs^^\n";
						break;
					}
				case 6:
					{
						stop=0;
						cout<<"\n\n****\n\n";
					}
			}
		}
			break;
		}
	case 3:
		{
			stop=1;
			Buyyer b;
			int ch;
			while(stop!=0)
			{
				system("color 20");
			cout<<"\n******Buyer********\n";
			cout<<"1-View Car\n";
			cout<<"2-Rent a Car\n";
			cout<<"3-Back\n";
			cin>>ch;
			string m;
			switch(ch)
			{
				case 1:
					{
							system("color 2F");
						i.display();
						cout<<"Enter m for main menu";
						cin>>m;
						break;
					}
				case 2:
					{
						cout<<"\n^^^^^^^^^^Avaliable Cars^^^^^^^^^^\n";
						i.display();
							system("color 2E");
						int id,days,Price;
						string name;
							cout<<"Enter Car id";
						cin>>id;
						if(i.search(id))
						{	
						cout<<"Enter your Name";
						cin>>name;
						cout<<"Day ";
						cin>>days;
						cout<<"Enter Price of 1 day";
						cin>>Price;
						cout<<"Total Price: "<<days*Price;
						b.InsertAtHead(id,name,days);	
						i.deleteNode(id);
						}
						else
						{
							cout<<"Sorry we this car is not avaliable";
						}
						
						
						break;
					}
//				case 3:
//					{
//							system("color E4");
//					b.Display();
//					break;
//					}
				case 3:
					{
						stop=0;
					}
			}
		}
			
			
			break;
		}

case 4:
	{
		system("color 0F");

cout<<"\n\n\n^^**The End**^^";
return 0;
		
	}
}
}


    return 0;
}
