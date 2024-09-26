# III. Abstract Class (คลาสนามธรรม) คืออะไร?

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

```python
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
