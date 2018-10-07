# StructExc8
Да се напише програма, която създава структура Automobile с полета brand, model, date, и price, указващи марка, модел, дата на производство и цена на автомобилите в автосалон. Да се въведе цяло число n и след него n на брой данни от тип Automobile. Да се изведат всички налични автомобили, сортирани по азбучен ред на марката автомобил.

#include<iostream>
#include<cstring>
#include <iomanip>
using namespace std;
struct Automobile
{
    string brand;
    string model;
    string date;
    double price;
};
int main()
{
    int n;
    Automobile temp;
    cout<<"Enter number of cars: ";
    cin>>n;
    Automobile automobile[n];
    for(int i=0;i<n;i++)
    {
        cout<<"*****Automobile*****"<<i+1<<endl;
        cout<<"Brand: ";
        cin>>automobile[i].brand;
        cout<<"Model: ";
        cin.get();
        cin>>automobile[i].model;
        cout<<"Date: ";
        cin>>automobile[i].date;
        cout<<"price: ";
        cin>>automobile[i].price;
    }
    for(int i=0;i<n-1;i++)
    {
        for(int j=i+1;j<n;j++)
        {
            if(automobile[i].brand>automobile[j].brand)
            {
                temp=automobile[i];
                automobile[i]=automobile[j];
                automobile[j]=temp;
            }
        }
    }
    for(int i=0;i<n;i++)
    {
        cout<<"*****Automobile "<<i+1<<"*****"<<endl;
        cout<<"Brand: "<<automobile[i].brand<<endl;
        cout<<"Model: "<<automobile[i].model<<endl;
        cout<<"Date : "<<automobile[i].date<<endl;
        cout<<"Price: "<<automobile[i].price<<endl;
    }
    
    system("pause");
    return 0;
}

// Същата задача решена чрез указател към структури

#include<iostream>
#include<cstring>
#include <iomanip>
using namespace std;
struct Automobile
{
    string brand;
    string model;
    string date;
    double price;
};
int main()
{
    int n;
    Automobile temp;
    cout<<"Enter number of cars: ";
    cin>>n;
    Automobile automobile[n];
    Automobile *q;
    q=automobile;
    for(int i=0;i<n;i++)
    {
            cout<<"Brand: ";
            cin>>q->brand;
            cout<<"Model: ";
            cin>>q->model;
            cout<<"Date: ";
            cin>>q->date;
            cout<<"Price: ";
            cin>>q->price;
            q++;
    }
    for(int i=0;i<n-1;i++)
    {
        for(int j=i+1;j<n;j++)
        {
            if(automobile[i].brand>automobile[j].brand)
            {
                temp=automobile[i];
                automobile[i]=automobile[j];
                automobile[j]=temp;
            }
        }
    }
    for(int i=0;i<n;i++)
    {
        cout<<"*****Automobile "<<i+1<<"*****"<<endl;
        cout<<"Brand: "<<automobile[i].brand<<endl;
        cout<<"Model: "<<automobile[i].model<<endl;
        cout<<"Date : "<<automobile[i].date<<endl;
        cout<<"Price: "<<automobile[i].price<<endl;
    }
    
    system("pause");
    return 0;
}
