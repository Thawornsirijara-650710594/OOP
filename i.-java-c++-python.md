# I. เขียนโปรแกรมในภาษา Java, C++, Python เปรียบเทียบผลรัน



## Java

```java
class Animal {
    Animal() {
        System.out.println("create animal");
    }

    void sound() {
        System.out.println("animal makes a sound");
    }

    protected void finalize() {
        System.out.println("delete animal");
    }
}

class Dog extends Animal {
    Dog() {
        System.out.println("dog");
    }

    @Override
    void sound() {
        System.out.println("dog barks");
    }

    protected void finalize() {
        System.out.println("delete dog");
    }
}

class Cat extends Animal {
    Cat() {
        System.out.println("cat");
    }

    @Override
    void sound() {
        System.out.println("cat meows");
    }

    protected void finalize() {
        System.out.println("delete cat");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a = new Animal();
        Dog d = new Dog();
        Cat c = new Cat();

        a.sound();
        d.sound();
        c.sound();
    }
}

```

```
create animal
create animal
dog
create animal
cat
animal makes a sound
dog barks
cat meows
```

* ข้อความ "delete animal", "delete dog", และ "delete cat" จะไม่แสดงใน output เนื่องจากการเก็บขยะ (garbage collection) ใน Java ทำงานในเวลาไม่แน่นอน

## C++

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    Animal() {
        cout << "create animal" << endl;
    }

    virtual void sound() {
        cout << "animal makes a sound" << endl;
    }

    virtual ~Animal() {
        cout << "delete animal" << endl;
    }
};

class Dog : public Animal {
public:
    Dog() {
        cout << "dog" << endl;
    }

    void sound() override {
        cout << "dog barks" << endl;
    }

    ~Dog() {
        cout << "delete dog" << endl;
    }
};

class Cat : public Animal {
public:
    Cat() {
        cout << "cat" << endl;
    }

    void sound() override {
        cout << "cat meows" << endl;
    }

    ~Cat() {
        cout << "delete cat" << endl;
    }
};

int main() {
    Animal* a = new Animal();
    Dog* d = new Dog();
    Cat* c = new Cat();

    a->sound();
    d->sound();
    c->sound();

    delete a;
    delete d;
    delete c;

    return 0;
}

```

```
create animal
create animal
dog
create animal
cat
animal makes a sound
dog barks
cat meows
delete cat
delete dog
delete animal
```



## Python

```python
class Animal:
    def __init__(self):
        print("create animal")

    def sound(self):
        print("animal makes a sound")

    def __del__(self):
        print("delete animal")


class Dog(Animal):
    def __init__(self):
        super().__init__()
        print("dog")

    def sound(self):
        print("dog barks")

    def __del__(self):
        print("delete dog")


class Cat(Animal):
    def __init__(self):
        super().__init__()
        print("cat")

    def sound(self):
        print("cat meows")

    def __del__(self):
        print("delete cat")

    a = Animal()
    d = Dog()
    c = Cat()

    a.sound()
    d.sound()
    c.sound()

```

```
create animal
create animal
dog
create animal
cat
animal makes a sound
dog barks
cat meows
```

* ใน Python, การลบออบเจ็กต์จะเกิดขึ้นเมื่อออบเจ็กต์นั้นไม่ได้ถูกอ้างถึงอีกต่อไป และ Python จะจัดการกับการเก็บขยะ (garbage collection) โดยอัตโนมัติ ดังนั้นข้อความ "delete animal", "delete dog", และ "delete cat" อาจไม่แสดงใน output ขึ้นอยู่กับว่าเมื่อไหร่ที่ Python เริ่มจัดการกับการเก็บขยะ. หากคุณต้องการให้เห็นการทำลายออบเจ็กต์อย่างชัดเจน คุณสามารถใช้ `del` เพื่อกำหนดให้ลบออบเจ็กต์ทันที

```python
del a
del d
del c
```
