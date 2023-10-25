#include <iostream>
#include <string>
#include <cmath>

class Parallelogram {
private:
    double base;
    double height;
    double side;
    std::string color;

public:
    // Конструктори
    Parallelogram() : base(0.0), height(0.0), side(0.0), color("White") {}
    Parallelogram(double base, double height, double side, std::string color) {
        if (base <= 0 || height <= 0 || side <= 0) {
            std::cerr << "Помилка: Основа, висота та бічна сторона повинні бути додатніми числами." << std::endl;
            exit(1);
        }
        this->base = base;
        this->height = height;
        this->side = side;
        this->color = color;
    }

    // Функції-члени обчислення площі та периметру
    double calculateArea() const {
        return base * height;
    }

    double calculatePerimeter() const {
        return 2 * (base + side);
    }

    // Функції-члени встановлення полів
    void setBase(double newBase) {
        if (newBase <= 0) {
            std::cerr << "Помилка: Основа повинна бути додатнім числом." << std::endl;
            return;
        }
        base = newBase;
    }

    void setHeight(double newHeight) {
        if (newHeight <= 0) {
            std::cerr << "Помилка: Висота повинна бути додатнім числом." << std::endl;
            return;
        }
        height = newHeight;
    }

    void setSide(double newSide) {
        if (newSide <= 0) {
            std::cerr << "Помилка: Бічна сторона повинна бути додатнім числом." << std::endl;
            return;
        }
        side = newSide;
    }

    void setColor(const std::string& newColor) {
        color = newColor;
    }

    // Функції-члени, що повертають значення полів
    double getBase() const {
        return base;
    }

    double getHeight() const {
        return height;
    }

    double getSide() const {
        return side;
    }

    std::string getColor() const {
        return color;
    }

    // Функція друку
    void printDetails() const {
        std::cout << "Паралелограм з основою " << base << ", висотою " << height << ", бічною стороною " << side << " та кольором " << color << std::endl;
        std::cout << "Площа: " << calculateArea() << std::endl;
        std::cout << "Периметр: " << calculatePerimeter() << std::endl;
    }
};

int main() {
    Parallelogram parallelogram1(5.0, 3.0, 4.0, "Синій");
    parallelogram1.printDetails();

    Parallelogram parallelogram2;
    parallelogram2.setBase(6.0);
    parallelogram2.setHeight(2.5);
    parallelogram2.setSide(4.5);
    parallelogram2.setColor("Червоний");
    parallelogram2.printDetails();

    return 0;
}
