# Инкапсуляция, наследование и полиморфизм
Инкапсуляция, наследование и полиморфизм — три основные концепции объектно-ориентированного программирования (ООП).
# Инкапсуляция
Инкапсуляция - это принцип, при котором данные и методы для работы с данными объединяются в одном классе. 
Внешние объекты могут взаимодействовать с ними только через публичные методы, то есть public. 
Пример будет на C++
___
```C++
using namespace std;


class Pet {
private:
    string name; 
    int age;

public:
    
    Pet(string n, int a) : name(n), age(a) {}

    // доступ к закрытой части для записи имени
    void setName(string n) {
        name = n;
    }

    // Публичный метод для получения имени
    string getName() const {
        return name;
    }

    // Публичный метод для доступа к возрасту
    int getAge() const {
        return age;
    }
};

int main() {
    Pet p("Arrow", 10);
    cout << "Name: " << p.getName() << ", Age: " << p.getAge() << endl;

    p.setName("Max");  // Изменение имени через метод
    cout << "Updated Name: " << p.getName() << endl;

    return 0;
}
```
___
# Наследование
 Наследование - это механизм, позволяющий одному классу использовать или расширять функциональность другого класса. Наследование позволяет избежать дублирования кода.
___
```C++
using namespace std;


class Animal {
public:
    void eat() {
        cout << "Animal is eating." << endl;
    }
};

class Dog : public Animal {
public:
    void bark() {
        cout << "Dog is barking." << endl;
    }
};

int main() {
    Dog myDog;
    myDog.eat();
    myDog.bark(); 
    return 0;
}
```
___
# Полиморфизм
Полиморфизм позволяет объектам различных классов обрабатываться единообразно, при этом вызываются методы, специфичные для каждого класса. Полиморфизм может быть реализован через виртуальные функции.
___
```C++
using namespace std;

class Animal {
public:
    virtual void sound() const {  
        cout << "Animal makes a sound." << endl;
    }
};

class Dog : public Animal {
public:
    void sound() const override {  // Переопределение метода
        cout << "Dog barks." << endl;
    }
};

class Cat : public Animal {
public:
    void sound() const override {  // Переопределение метода
        cout << "Cat meows." << endl;
    }
};

void makeSound(const Animal& animal) {
    animal.sound();  // Вызывается правильная версия метода
}

int main() {
    Dog dog;
    Cat cat;

    makeSound(dog);  // Полиморфизм: вызов метода Dog::sound()
    makeSound(cat);  // Полиморфизм: вызов метода Cat::sound()

    return 0;
}
```
___

# Исправление ошибки в последнем коммите

Для сброса можно использовать ```git reset``` вместе с параметром --hard и HEAD или хэш коммита, к которому надо вернуться.
Просмотр логов - ```git log```.
Если надо сохранить историю, то можно использовать ```git revert``` вместе с HEAD.
Для отката незакоммиченных изменений - ```git restore```

___
# Палиндром
```C++
#include <iostream>
#include <string>
#include <algorithm>

using namespace std;

bool isPalindrome(const string& str) {
    string cleanedStr;

    for (char ch : str) {
        if (isalnum(ch)) {  // Буква или цифра
            cleanedStr += tolower(ch);
        }
    }

    // Сравниваем  строку с её перевернутой версией
    string reversedStr = cleanedStr;
    reverse(reversedStr.begin(), reversedStr.end());

    return cleanedStr == reversedStr;
}

int main() {
    string input;
    cout << "Введите строку: ";
    getline(cin, input);

    if (isPalindrome(input)) {
        cout << "Это палиндром." << endl;
    } else {
        cout << "Это не палиндром." << endl;
    }

    return 0;
}
```
___

# Опыт в IT
В основном опыт у меня от практики от Вуза, но буст к знаниям дали курсы по программированию и различные ресурсы в интернете. 9 месяцев работал в Яндексе в качестве тестировщика, там понял как работать с программой charles. 
