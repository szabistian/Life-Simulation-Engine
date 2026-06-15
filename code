#include <iostream>
#include <string>
#include <cstdlib>
#include <ctime>

using namespace std;

// ====================== CHARACTER CLASS ======================
class Character {
private:
    int health;
    int energy;
    int money;
    int skill;
    int happiness;

public:
    Character() {
        health = 70;
        energy = 70;
        money = 100;
        skill = 20;
        happiness = 60;
    }

    void showStats() {
        cout << "\n===== CURRENT STATS =====\n";
        cout << "Health: " << health << endl;
        cout << "Energy: " << energy << endl;
        cout << "Money: " << money << endl;
        cout << "Skill: " << skill << endl;
        cout << "Happiness: " << happiness << endl;
        cout << "=========================\n";
    }

    void study() {
        skill += 10;
        energy -= 10;
        happiness -= 5;
        cout << "You studied hard today.\n";
    }

    void work() {
        money += 20;
        energy -= 15;
        happiness -= 5;
        cout << "You worked and earned money.\n";
    }

    void rest() {
        energy += 20;
        happiness += 5;
        cout << "You took rest and recovered energy.\n";
    }

    void exercise() {
        health += 10;
        energy -= 10;
        happiness += 5;
        cout << "You exercised and improved health.\n";
    }

    void randomEvent() {
        int event = rand() % 3;

        if (event == 0) {
            cout << "Lucky Event: You found money!\n";
            money += 30;
        }
        else if (event == 1) {
            cout << "Bad Event: You got sick!\n";
            health -= 15;
            energy -= 10;
        }
        else {
            cout << "Neutral Day: Nothing special happened.\n";
        }
    }

    bool isAlive() {
        return (health > 0 && energy > 0);
    }

    void limitStats() {
        if (health > 100) health = 100;
        if (energy > 100) energy = 100;
        if (happiness > 100) happiness = 100;
        if (skill > 100) skill = 100;

        if (health < 0) health = 0;
        if (energy < 0) energy = 0;
        if (happiness < 0) happiness = 0;
    }

    void finalReport() {
        cout << "\n\n===== FINAL REPORT =====\n";
        cout << "Final Health: " << health << endl;
        cout << "Final Energy: " << energy << endl;
        cout << "Final Money: " << money << endl;
        cout << "Final Skill: " << skill << endl;
        cout << "Final Happiness: " << happiness << endl;

        if (skill > 70 && happiness > 50)
            cout << "\nOutcome: Successful Balanced Life!\n";
        else if (money > 150)
            cout << "\nOutcome: Financially Successful Life!\n";
        else if (health < 40)
            cout << "\nOutcome: Unhealthy Burnout Life!\n";
        else
            cout << "\nOutcome: Average Life Results.\n";

        cout << "=========================\n";
    }
};

// ====================== GAME CLASS ======================
class Game {
private:
    Character player;
    int days;

public:
    Game() {
        days = 10;
    }

    void start() {
        cout << "===== LIFE SIMULATION ENGINE =====\n";

        for (int i = 1; i <= days; i++) {
            if (!player.isAlive()) {
                cout << "\nGame Over! Your character cannot continue.\n";
                break;
            }

            cout << "\n\n===== DAY " << i << " =====\n";
            player.showStats();

            int choice;
            cout << "\nChoose Action:\n";
            cout << "1. Study\n2. Work\n3. Rest\n4. Exercise\n";
            cout << "Enter choice: ";
            cin >> choice;

            switch (choice) {
                case 1: player.study(); break;
                case 2: player.work(); break;
                case 3: player.rest(); break;
                case 4: player.exercise(); break;
                default:
                    cout << "Invalid choice! You wasted the day.\n";
                    break;
            }

            player.randomEvent();
            player.limitStats();
        }

        player.finalReport();
    }
};

// ====================== MAIN FUNCTION ======================
int main() {
    srand(time(0));

    Game game;
    game.start();

    return 0;
}
