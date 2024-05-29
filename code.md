"# Praktikum-2" 
#include <iostream>

class basic_stat {
private:
    int hp;
    int def;
    int att;

public:
    basic_stat(int nyawa, int defend, int serang) : hp(nyawa), def(defend), att(serang) {}

    virtual void displayinfo() {
        std::cout << "nyawa = " << hp << std::endl;
        std::cout << "defend = " << def << std::endl;
    }

    int getHP() {
        return hp;
    }

    int getDef() {
        return def;
    }

    int getAtt() {
        return att;
    }
};

class greatsword : public basic_stat {
public:
    greatsword(int nyawa, int defend, int serang) : basic_stat(nyawa, defend, serang) {}

    void displayinfo() override {
        std::cout << "HP: " << getHP() << std::endl;
        std::cout << "Attack: " << getAtt() << std::endl;
        std::cout << "Defense: " << getDef() << std::endl;
    }
};

int main() {
    greatsword Alice(100, 2, 30);
    Alice.displayinfo(); 
    return 0;
}
