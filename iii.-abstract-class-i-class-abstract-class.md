# III. abstract class คืออะไร ในตัวอย่างข้อ I ที่ให้ class ใดคือ abstract class และมีหลักการสร้างอย่าง

**Abstract Class** คือคลาสที่ไม่สามารถสร้างอินสแตนซ์ (object) ได้โดยตรง และมักถูกใช้เป็นแม่แบบสำหรับคลาสอื่น ๆ โดยมีเมธอดที่ไม่มีการใช้งาน (abstract methods) ซึ่งต้องถูกกำหนดในซับคลาส (derived classes) ที่สืบทอดจากคลาสนี้

#### คุณสมบัติของ Abstract Class

* ไม่สามารถสร้างออบเจ็กต์จากคลาสนี้ได้
* สามารถมีเมธอดที่มีการใช้งาน (concrete methods) และเมธอดที่ไม่มีการใช้งาน (abstract methods)
* ซับคลาสต้อง implement เมธอดนามธรรมที่ประกาศในคลาสนามธรรม

```java
abstract class Animal {
    Animal() {
        System.out.println("create animal");
    }

    abstract void sound(); 

    protected void finalize() {
        System.out.println("delete animal");
    }
}
```

```cpp
class Animal {
public:
    Animal() {
        cout << "create animal" << endl;
    }

    virtual void sound() = 0; 

    virtual ~Animal() {
        cout << "delete animal" << endl;
    }
};
C++ จะใช้การประกาศเมธอดด้วย = 0 เพื่อทำให้เมธอดเป็น abstract:
```

```python
class Animal(ABC):
    def __init__(self):
        print("create animal")

    @abstractmethod
    def sound(self):  
        pass
```

* ใน Java คลาสที่เป็น abstract class ถูกประกาศด้วยคำว่า `abstract`
* ใน C++ การทำให้เมธอดเป็นนามธรรมใช้การกำหนด `= 0` และคลาสที่มีเมธอดเช่นนี้เรียกว่า "pure virtual class" ซึ่งทำหน้าที่เป็นแม่แบบเช่นเดียวกับ abstract class ใน Java
* ใน Python เราสามารถใช้คลาส `ABC` (Abstract Base Class) และตกแต่งเมธอดด้วย `@abstractmethod` เพื่อทำให้เป็นนามธรรม
