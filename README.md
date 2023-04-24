# C-Users-satthirathomp_snhu-Source-Repos-NewRepo2
#include <iostream> //Start standard Streaming imput
#include <fstream>  //include stream file header
#include <map>   //map header file
#include <string>  //String header file

using namespace std;

class GroceryItems {
	private:
	   map <string, int> frequency;
	public:
		//Read and store freguency of each items from file
	   void processfileinput(string filename) {
		ifstream fileInput(filename);
	   if (fileinput.fail()) {
            	cout << "Error" << filename << endl;
            	return;
	   }
	   Sting item:
	   while(fileInput>> item){
	       freqItems[item]++;
	   }
	   fileInput.close(); // close input file

	}

	// calculate the frequency of a listed item
    
	int getItemFrequency(string item) {
         
 	return freqItems[item];

	}
 	// Prints a list of frequent items
    	void printFrequentList() {
        for (auto it = freqitems.begin(); it != freqitems.end(); ++it) {
            cout << it->first << ": " << it->second << endl;
        }
   }
 	// Print a histogram of all frequent items 
   	 void printHistogram() {
        for (auto = freqitems.begin(); it != freqitems.end(); ++it) {
            cout << it->first << " ";
            for (int i = 0; i < it->second; i++) {
                cout << "*";
            }
            cout << endl;
        }
    }
	void backupFrequencyData(string filename) { //Writes the caculated data to the backup file
           ofstream outputfreqitems(filename);
           if (output.fail()) {
            cout << "Error" << filename << endl;
            return;
        }
        for (auto it = freqitem.begin(); it != freqitem.end(); ++it) {
            output << it-> first << ": " << it->second << endl;
        }
	 output.close();
    }
int main() {
    GroceryItems;

    // Process the file input
    grocery.processFileInput("CS210_Project_Three_Input_File.txt");

    // Main menu loop
    boolean running = true;
    while (running) {
        // Display menu options
        cout << "\n Menu options endl;
        cout << "Select an option:" << endl;
        cout << "1. Look up an item's frequency" << endl;
        cout << "2. Print list of all items and frequencies" << endl;
        cout << "3. Print histogram of item frequencies" << endl;
        cout << "4. Exit the program" << endl;

        // Get user input
        int choice;
        cout << "Enter your choice (1-4): ";
        cin >> choice;
	return input;
 }

        // Perform action based on user input
        switch (choice) {
            case 1: {
                string item;
                cout << "Enter the item to look up: ";
                cin >> item;
                int freq = grocery.getItemFrequency(item);
                cout << "Frequency of " << item << ": " << freq << endl;
                break;
            }
            case 2: {
                grocery.printFrequencyList();
                break;
            }
            case 3: {
                grocery.printHistogram();
                break;
            }
            case 4: {
                grocery.backupFrequencyData("frequency.dat");
                running = false;
                break;
            }
            default: {
                cout << "Invalid choice. Please enter a number between 1 and 4." << endl;
               break;
            }
        }
    }
    return 0;
}
