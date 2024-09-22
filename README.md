---
description: >-
  เปรียบเทียบความเหมือนและความแตกต่างในการเขียนโปรแกรมแบบ OOP ด้วยภาษา Java,
  C++, Python
---

# OOP Java, Python and C++

My Github

{% embed url="https://github.com/Thawornsirijara-650710594" %}

My Repository

{% embed url="https://github.com/Thawornsirijara-650710594/OOP" %}

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



## ส่วนของความเหมือนและความแตกต่าง

ในการเขียน OOP ของภาษา Java, Python และ C++



### ความเหมือน

* **หลักการ OOP**: ทั้งสามภาษานิยมใช้หลักการ OOP เช่น การสร้างคลาส, การสร้างอ็อบเจกต์, การสืบทอด (inheritance) และการโอเวอร์ไรด์ (override) เมธอด
* **คอนสตรัคเตอร์และเดสตรัคเตอร์**: ในแต่ละภาษา, คลาส `Animal`, `Dog`, และ `Cat` มีคอนสตรัคเตอร์เพื่อแสดงข้อความเมื่อสร้างอ็อบเจกต์ และเดสตรัคเตอร์เพื่อแสดงข้อความเมื่อทำลายอ็อบเจกต์
* **การโอเวอร์ไรด์เมธอด**: การโอเวอร์ไรด์เมธอด `sound` ใน `Dog` และ `Cat` เพื่อแสดงเสียงที่แตกต่างกันทำให้โปรแกรมมีความยืดหยุ่นและสามารถใช้งานได้ตามต้องการ

### ความต่าง

* **การจัดการ**:
  * วิธีการจัดการหน่วยความจำมีความแตกต่างกัน โดย Java และ Python มีการจัดการอัตโนมัติ ในขณะที่ C++ ต้องทำด้วยตนเอง
  * **Java และ Python:** ทั้งสองภาษาใช้ระบบจัดการหน่วยความจำอัตโนมัติ ทำให้ไม่จำเป็นต้องจัดการกับการลบอ็อบเจกต์ด้วยตัวเอง &#x20;

<pre class="language-java"><code class="lang-java">public class Main {
    public static void main(String[] args) {
        Animal a = new Animal();
        Dog d = new Dog();
        Cat c = new Cat();

        a.sound();
        d.sound();
        c.sound();
<strong>    }
</strong></code></pre>

```python
    a = Animal()
    d = Dog()
    c = Cat()

    a.sound()
    d.sound()
    c.sound()
```

```cpp
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

* **การสืบทอด (Inheritance)**:
  * **Java**: ใช้คำสั่ง `extends` เพื่อสืบทอดคลาส
  * **C++**: ใช้เครื่องหมาย `:` และระบุการสืบทอดว่าเป็นแบบ `public`, `protected`, หรือ `private`
  * **Python**: ใช้การใส่ชื่อคลาสพ่อในวงเล็บหลังชื่อคลาสลูก
* **การกำหนดฟังก์ชันโอเวอร์ไรด์**:
  * **Java**: ใช้คำสั่ง `@Override` เพื่อระบุว่าเป็นการโอเวอร์ไรด์เมธอด
  * **C++**: ใช้คำว่า `override` หลังจากการประกาศฟังก์ชัน
  * **Python**: ไม่ต้องใช้คำสำคัญพิเศษ เพียงแค่ประกาศฟังก์ชันใหม่ในคลาสลูกที่มีชื่อเดียวกับฟังก์ชันในคลาสพ่อ
* **การแสดงผล**:
  * **Java**: ใช้ `System.out.println()` สำหรับการแสดงผล
  * **C++**: ใช้ `cout` สำหรับการแสดงผล
  * **Python**: ใช้ `print()` สำหรับการแสดงผล
