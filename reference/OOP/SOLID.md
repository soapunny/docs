# SOLID
<br/>

### __SRP__
+ Single Responsibility Principl(단일 책임 원칙)
+ An object should have only one responsibility.
+ It helps to achieve high cohesiveness(The processing functions are interrelated well in a module) and low coupling(Changes in one module do not affect other modules).

    ```java
    public class Car{
        public void drive(){}
        public void stop(){}
        public void fly(){}// => It violates the SRP.
    };
    ```
<br/>


### __OCP__
+ Open-Closed Principle(개방-폐쇄 원칙)
+ Closed to changing the existing code, open to adding new functions(수정에 폐쇄적, 확장에 개방적)
+ Define the sharing functions used by multiple objects in an interface with encapsulation.
    
    ```java
    public interface Driving{
        void drive();
        void stop();
    }
    public interface AC{
        void turnOnAC();
        void turnOffAC();
    }
    public class Car implements Driving, AC{
        public void drive(){}
        public void stop(){}
        public void turnOnAC(){}
        public void turnOffAC(){}
    }
    public class MyHouse implements AC{
        public void turnOnAC(){}
        public void turnOffAC(){}
    }
    ```
<br/>


### __LSP__
+ Liskov Substitution Principle(리스코프 대안 원칙)
+ A child class should always be able to take over the role of a parent class.(자식 클래스는 부모 클래스의 역할을 전부 수행)
+ A child class should not ignore or override the parents functions.(부모 클래스의 기능을 무시하거나 오버라이드 x)
<br/>


### __ISP__
+ Interface Segregation Principle(인터페이스 분리 원칙)
+ Don't implement interfaces you don't use.(자신이 사용하지 않는 인터페이스는 구현 x)
+ Multiple concrete interfaces are better than one huge interface.(하나의 큰 인터페이스 보다 여러개의 구체적인 인터페이스가 낫다)
    ```java
    //Bad example
    public interface Car{
        void drive();
        void stop();
        void turnOnAC();
        void turnOffAC();
        void turnOnAutonomousDriving();
        void turnOffAutonomousDriving();
    }
    public class ManualCar implements Car{
        public void drive(){}
        public void stop(){}
        public void turnOnAC(){}
        public void turnOffAC(){}
        public void turnOnAutonomousDriving(){}// doesn't have this function in this car.
        public void turnOffAutonomousDriving(){}// violates the ISP
    }
    
    //Good example
    public interface Driving{
        void drive();
        void stop();
    }
    public interface AC{
        void turnOnAC();
        void turnOffAC();
    }
    public interface AutonomousDriving{
        void turnOnAutonomousDriving();
        void turnOffAutonomousDriving();
    }
    public class Car implements Driving, AC{
        public void drive(){}
        public void stop(){}
        public void turnOnAC(){}
        public void turnOffAC(){}
    }
    public class AutonomousCar extends Car implements AutonomousDriving{
        //public void drive(){} //Doesn't override the parent's functions(LSP)
        //public void stop(){}
        //public void turnOnAC(){}
        //public void turnOffAC(){}
        public void turnOnAutonomousDriving(){}
        public void turnOffAutonomousDriving(){}
    }
    ```
<br/>


### __DIP__
+ Dependency Inversion Principle(의존 역전 원칙)
+ A class must have a dependency on a class with a higher abstraction level than a class with a lower level of abstraction(클래스는 추상성이 낮은 클래스보다 추상성이 높은 클래스와 의존 관계를 맺어야 한다).
    ```java
    public class Me{
        //Depends on higher abstraction level class. Instead of "AutonomousCar"
        private Car myCar;
        
        public Me(){
            myCar = new AutonomousCar();
        }
    }
    ```
<br/>