#include <iostream>
#include <vector>
#include <unordered_map>
#include <random>
#include <unistd.h>
using namespace std;

class engineStarter {
    private:
    mt19937 rng;
    vector<string>trigs = {"sin ", "cos ", "tan "};
    vector<string>possible_angles = {"0", "30", "45", "60", "90", "120", "135", "150", "180", "210", "225", "240", "270", "300", "315", "330", "360"};
    unordered_map<string, string>combinations = {
        {"sin 0", "0"},
        {"cos 0", "1"},
        {"tan 0", "0"},
        {"sin 30", "1/2"},
        {"cos 30", "rad3/2"},
        {"tan 30", "rad3/3"},
        {"sin 45", "rad2/2"},
        {"cos 45", "rad2/2"},
        {"tan 45", "1"}, 
        {"sin 60", "rad3/2"},
        {"cos 60", "1/2"},
        {"tan 60", "rad3"},
        {"sin 90", "1"},
        {"cos 90", "0"},
        {"tan 90", "und"},
        {"sin 120", "rad3/2"},
        {"cos 120", "-1/2"},
        {"tan 120", "-rad3"},
        {"sin 135", "rad2/2"},
        {"cos 135", "-rad2/2"},
        {"tan 135", "-1"},
        {"sin 150", "1/2"},
        {"cos 150", "-rad3/2"},
        {"tan 150", "-rad3/3"},
        {"sin 180", "0"},
        {"cos 180", "-1"},
        {"tan 180", "0"},
        {"sin 210", "-1/2"},
        {"cos 210", "-rad3/2"},
        {"tan 210", "rad3/3"},
        {"sin 225", "-rad2/2"},
        {"cos 225", "-rad2/2"},
        {"tan 225", "1"},
        {"sin 240", "-rad3/2"},
        {"cos 240", "-1/2"},
        {"tan 240", "rad3"}, //"270", "300", "315", "330", "360"};
        {"sin 270", "-1"},
        {"cos 270", "0"},
        {"tan 270", "und"},
        {"sin 300", "-rad3/2"},
        {"cos 300", "1/2"},
        {"tan 300", "-rad3"},
        {"sin 315", "-rad2/2"},
        {"cos 315", "rad2/2"},
        {"tan 315", "-1"},
        {"sin 330", "-1/2"},
        {"cos 330", "rad3/2"},
        {"tan 330", "-rad3/3"},
        {"sin 360", "0"},
        {"cos 360", "1"},
        {"tan 360", "0"}

    };
    public:

    engineStarter() {
        rng.seed(random_device{}());
    }

    void loopfunc() {
        int highscore = 0;
        int points = 0;
        string correctAns = "";
        string correctTrig = "";
        while(true) {
            string resultant = RandomTrig() + RandomAng();
            string userInput;

            if(!correctAns.empty())
                cout << "Correct Answer " << correctTrig << " = " << correctAns << endl;

            cout << "HighScore: " << highscore << endl << "Current Score: " << points << endl << "Find: " << resultant << endl;
            getline(cin, userInput);

            if(userInput == "exit")
                break;


            auto it = combinations.find(resultant);
            if(it != combinations.end() && it->second == userInput) {
                correctAns = "";
                correctTrig = "";
                points++;
            } else {
                if(highscore <= points) {
                    highscore = points;
                }
                correctAns = it->second;
                correctTrig = it->first;
                points = 0;
            }
            system("clear");
            
        }
    }

    string& RandomTrig() {
        uniform_int_distribution<size_t> gen(0, trigs.size() - 1);
        return trigs[gen(rng)];
    }

    string& RandomAng() {
        uniform_int_distribution<size_t> gen(0, possible_angles.size() - 1);
        return possible_angles[gen(rng)];
    }

};

int main () {
    engineStarter obj1;
    obj1.loopfunc();

    
}
