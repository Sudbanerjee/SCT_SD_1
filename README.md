# SCT_SD_1



#include <iostream>

using namespace std;

double CelsiusToFahrenheit(double celsius) {
    return (celsius * 9/5) + 32;
}

double CelsiusToKelvin(double celsius) {
    return celsius + 273.15;
}

double FahrenheitToCelsius(double fahrenheit) {
    return (fahrenheit - 32) * 5/9;
}

double FahrenheitToKelvin(double fahrenheit) {
    return (fahrenheit - 32) * 5/9 + 273.15;
}

double KelvinToCelsius(double kelvin) {
    return kelvin - 273.15;
}

double KelvinToFahrenheit(double kelvin) {
    return (kelvin - 273.15) * 9/5 + 32;
}

int main() {
    double temperature;
    char currentScale, targetScale;
    
    cout << "Enter the temperature: ";
    cin >> temperature;
    cout << "Enter the current scale (C for Celsius, F for Fahrenheit, K for Kelvin): ";
    cin >> currentScale;
    cout << "Enter the target scale (C for Celsius, F for Fahrenheit, K for Kelvin): ";
    cin >> targetScale;
    
    double convertedTemperature;

    if (currentScale == 'C' || currentScale == 'c') {
        if (targetScale == 'F' || targetScale == 'f') {
            convertedTemperature = CelsiusToFahrenheit(temperature);
        } else if (targetScale == 'K' || targetScale == 'k') {
            convertedTemperature = CelsiusToKelvin(temperature);
        } else {
            cout << "Invalid target scale!";
            return 1;
        }
    } else if (currentScale == 'F' || currentScale == 'f') {
        if (targetScale == 'C' || targetScale == 'c') {
            convertedTemperature = FahrenheitToCelsius(temperature);
        } else if (targetScale == 'K' || targetScale == 'k') {
            convertedTemperature = FahrenheitToKelvin(temperature);
        } else {
            cout << "Invalid target scale!";
            return 1;
        }
    } else if (currentScale == 'K' || currentScale == 'k') {
        if (targetScale == 'C' || targetScale == 'c') {
            convertedTemperature = KelvinToCelsius(temperature);
        } else if (targetScale == 'F' || targetScale == 'f') {
            convertedTemperature = KelvinToFahrenheit(temperature);
        } else {
            cout << "Invalid target scale!";
            return 1;
        }
    } else {
        cout << "Invalid current scale!";
        return 1;
    }
    
    cout << "The converted temperature is: " << convertedTemperature << " " << targetScale << endl;

    return 0;
}
