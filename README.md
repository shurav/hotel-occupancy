# hotel-occupancy
This program allows the user to calculate the percent of rooms occupied per floor in the hotel

#include <iostream>
using namespace std;

int main()
{
    int numFloors; // number of floors in the hotel
    double numRooms; // number of rooms in the floor
    double numOccupied; // number of rooms occupied in the floor
    double percentOccupiedInFloor = 0; // percentage of rooms occupied in the floor
    cout << "This program will allow you to show how many rooms are occupied per floor in the hotel" << endl;
    cout << "Provide the number of floors in the hotel (Number of floors can't be less than 1): ";
    cin >> numFloors;
    while(numFloors <= 0) // while loop ensures the user entered the number of floors greater than 0
    {
        cout << "Please reenter a number greater than 0: ";
        cin >> numFloors;
    }
    for(int i = 0; i < numFloors; i++) // for loop iterates through the number of floors to determine percent of rooms occupied per floor
    {
        cout << "How many rooms are in floor " << i+1 << "? ";
        cin >> numRooms;
        while(numRooms <= 0)
        {
            cout << "Please reenter the number of rooms greater than 0: ";
            cin >> numRooms;
        }
        cout << "How many of them are occupied? ";
        cin >> numOccupied;
        while(numOccupied < 0 || numOccupied > numRooms)
        {
            cout << "Please renter a valid entry: ";
            cin >> numOccupied;
        }
        percentOccupiedInFloor = numOccupied/numRooms*100;
        cout << "The percentage of rooms occupied in floor " << i+1 << " is " << percentOccupiedInFloor << "%" << endl;
    }
    return 0;
}
