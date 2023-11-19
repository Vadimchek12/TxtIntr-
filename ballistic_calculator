#include <iostream>
#include <iomanip>
#include <cmath>
#include <string>
#include <getopt.h>

void printUsage()
{
    std::cout << "Баллистический калькулятор :)" << std::endl;
    std::cout << "Выберете операцию:" << std::endl;
    std::cout << " 1. Вычисление высоты полета: -o h (начальная скорость) (угол в градусах)" << std::endl;
    std::cout << " 2. Вычисление дистанции полета: -o d (начальная скорость) (угол в градусах)" << std::endl;
}

// Функция для вычисления высоты
double calculateHeight(double initialVelocity, double angle)
{
    const double g = 9.8; // Ускорение свободного падения
    return pow(initialVelocity, 2) * pow(sin(angle), 2) / (2 * g);
}

// Функция для вычисления дальности
double calculateDistance(double initialVelocity, double angle)
{
    const double g = 9.8; // Ускорение свободного падения
    return pow(initialVelocity, 2) * sin(2 * angle) / g;
}

int main(int argc, char* argv[])
{
    // Получение входных данных из командной строки
    double heightAngle = std::stod(argv[4]);
    double heightVelocity = std::stod(argv[3]);
    double distanceAngle = std::stod(argv[4]);
    double distanceVelocity = std::stod(argv[3]);
   
    std::string operation;
    double result = 0;

    struct option longOptions[] = {
        {"операция", required_argument, nullptr, 'o'},
        {nullptr, 0, nullptr, 0}
    };
    int optionIndex;
    int option;
    while ((option = getopt_long(argc, argv, "o:", longOptions, &optionIndex)) != -1) {
        switch (option) {
        case 'o':
            operation = optarg;
            break;
        default:
            printUsage();
            return 1;
        }
    }
    if (argc - optind < 2 || operation.empty()) {
        printUsage();
        return 1;
    }
    for (int i = optind; i < argc; i++) {
        double operand = std::stod(argv[i]);
        if (operation == "h") {
            result = calculateHeight(heightVelocity, heightAngle);
        } else if (operation == "d") {
            result = calculateDistance(distanceVelocity, distanceAngle);
        } else if (operation != "h" && operation != "d") {
            std::cout << "Некорректная операция: " << operation << std::endl;
            printUsage();
            return 1;
        }
    }
    std::cout << "Результат :) \n\n" << std::setprecision(4) << result << std::endl;
    return 0;
}
