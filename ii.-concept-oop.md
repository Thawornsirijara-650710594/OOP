# II. ทำความเข้าใจส่วนประกอบของโค้ดเปรียบเทียบกับ concept ของ OOP ต่อไปนี้ โดยยกตัวอย่างส่วนประกอบของโค้ดประกอบการอธิบาย

**1. Class (คลาส)**

* **คำอธิบาย**: คลาสคือแม่แบบที่ใช้ในการสร้างออบเจ็กต์ ซึ่งกำหนดคุณสมบัติและพฤติกรรม
* **ตัวอย่างโค้ด**:

```java
class Animal {
    Animal() {
        System.out.println("create animal");
    }
    
    void sound() {
        System.out.println("animal makes a sound");
    }
}
```

```python
class Animal:
    def __init__(self):
        print("create animal")
    
    def sound(self):
        print("animal makes a sound")
```

```cpp
class Animal {
public:
    Animal() {
        cout << "create animal" << endl;
    }

    void sound() {
        cout << "animal makes a sound" << endl;
    }
};
```

**2. Object / Instance (ออบเจ็กต์ / อินสแตนซ์)**

* **คำอธิบาย**: ออบเจ็กต์คือการจำลองเฉพาะของคลาส ซึ่งสร้างจากแม่แบบคลาส
* **ตัวอย่างโค้ด**:

```java
Animal a = new Animal();
```

```python
a = Animal()
```

```cpp
Animal* a = new Animal();
```

**3. Subclass / Derived Class (ซับคลาส / คลาสอนุพันธ์)**

* **คำอธิบาย**: ซับคลาสคือคลาสที่สืบทอดคุณสมบัติและพฤติกรรมจากคลาสแม่
* **ตัวอย่างโค้ด**

```java
class Dog extends Animal {
    Dog() {
        System.out.println("dog");
    }
}
```

```python
class Dog(Animal):
    def __init__(self):
        super().__init__()
        print("dog")
```

```cpp
class Dog : public Animal {
public:
    Dog() {
        cout << "dog" << endl;
    }
};
```

**4. Message (ข้อความ)**

* **คำอธิบาย**: ข้อความใน OOP หมายถึงการเรียกใช้เมธอดของออบเจ็กต์
* **ตัวอย่างโค้ด**:

```java
a.sound();
```

```python
a.sound()
```

```cpp
a->sound();
```

**5. Inheritance (การสืบทอด)**

* **คำอธิบาย**: การสืบทอดอนุญาตให้ซับคลาสสามารถสืบทอดคุณสมบัติและเมธอดจากซูเปอร์คลาส
* **ตัวอย่างโค้ด**:

```java
class Cat extends Animal {
    Cat() {
        System.out.println("cat");
    }
}
```

```python
class Cat(Animal):
    def __init__(self):
        super().__init__()
        print("cat")
```

```cpp
class Cat : public Animal {
public:
    Cat() {
        cout << "cat" << endl;
    }
};
```

**6. Polymorphism (พหุลักษณ์)**

* **คำอธิบาย**: พหุลักษณ์อนุญาตให้มีการใช้ออบเจ็กต์หลายประเภทซึ่งมีเมธอดที่ชื่อเดียวกัน
* **ตัวอย่างโค้ด**:

```java
Animal a = new Dog();
a.sound();
```

```python
a = Dog() 
a.sound() 
```

```cpp
Animal* a = new Dog(); 
a->sound(); 
```
