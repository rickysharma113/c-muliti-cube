#include <iostream>

using namespace std;
class Volume {
    public:
        float volume(float l, float b, float h) {
            return (l * b * h);
        }
};


class Area {
    public:
        float area(float l, float b, float h) {
            return (2 * (l * b + b * h + h * l));
        }
};

class Cuboid: private Volume, private Area {
    private: float length,
    breadth,
    height;

    
     public: 
    void getDimensions() {
        cout << "\nEnter the length of the Cuboid: ";
        cin >> length;

        cout << "\nEnter the breadth of the Cuboid: ";
        cin >> breadth;

        cout << "\nEnter the height of the Cuboid: ";
        cin >> height;

    }
    float volume() {


      return Volume::volume(length, breadth, height);
    }

    float area() {
        return Area::area(length, breadth, height);    }
};
int main() {
    cout <<   "Find Area & Volume of a Cuboid volume \n";
    Cuboid cuboid;
    cuboid.getDimensions();
    cout << "\n";
    cout <<  "Find Area & Volume of a Cuboid\n\n";
    cout << "\nArea of the Cuboid\n\n" <<"Volume of the Cuboid"<< "\n\n";
    cout <<"\n"<<cuboid.area()<<"\n\n\n\n"<<cuboid.volume()<< "\n\n";

    return 0;
}
