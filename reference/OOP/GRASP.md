# GRASP

+ General Responsibility Assignment Software Pattern
+ Grants each object reponsibility.
+ Has 9 principles
<br/><br/>

### __Information Expert(정보 담당자)__

``` Assigning responsibility to the object that has the most information to carry out the responsibility ```

```java
public class Car{
    public void drive(){}
    public void stop(){}
}
public class Me{
    private Car myCar = new Car();
}
public class MyDog{}// It doesn't have responsibility to my car.
```
<br/>

### __Creator__
``` who owns object "A" and instantiate it? In case```
+ it includes "A" or combines it.
+ it writes "A".
+ it uses "A" closely.
+ it has the initial value of "A".

```java
public class Car{
    private boolean isLocked;
    private Place currentParkingSpot;

    public void drive(){}
    public void stop(){}
    public void lock(){
        this.isLocked = true;
    }
    public void park(Place currentParkingSpot){
        this.currentParkingSpot = currentParkingSpot;
    }
}
public class Me{
    private Car myCar = new Car();//Me has a car

    public void goWork(){
        myCar.drive();//uses it's functions
        myCar.stop();
        myCar.park(Place.MY_HOME);// Me writes myCar.
        myCar.lock();
    }

}
```
<br/>

### __Controller__
``` Objects that receive and manage system control behind the UI layer ```
+ “System” as a whole, “top-level object”, software or the most central subsystem.
+ Expressing user use-cases that make up system behavior.

```java
public class CarController{
    private Car car = new Car();
    private CarModel carModel = new CarModel();

    public Coordination parkCar(Place destination){
        Coordination coor = null;
        try{
            coor = carModel.parkCar(car, destination);
            if(coor != null)
                throw new ParkingException("Parking Error");
        }catch(Exception e){
            e.printStackTrace();
        }
        return coor;
    }
}
```

<br/>

### __Low Coupling__
``` Reduce the interdependence between objects ```
+ Divide roles with concrete interfaces

```java
public interface Driving{
    void drive();
    void stop();
}
public interface FuelPort{
    void openFuelPort();
    void closeFuelPort();
}
public interface Trunk{
    void openTrunk();
    void closeTrunk();
}

public class Car implements Driving, FuelPort, Trunk{
    public void drive(){}
    public void stop(){}
    public void openFuelPort(){}
    public void closeFuelPort(){}
    public void openTrunk(){}
    public void closeTrunk(){}
}

public class Motobike implements Driving, FuelPort{
    public void drive(){}
    public void stop(){}
    public void openFuelPort(){}
    public void closeFuelPort(){}
}
```
<br/>

### __High Cohesion__
``` Each object consists of only closely related responsibilities ```
```java
public class Car implements Driving, FuelPort, Trunk{
    public void drive(){}
    public void stop(){}
    public void openFuelPort(){}
    public void closeFuelPort(){}
    public void openTrunk(){}
    public void closeTrunk(){}
    public void fly(){} // ? Not related responsibility. => causes low cohesion.
}
```
<br/>

### __Polymorphism__
``` Use an Strategy Pattern to use another type ```
```java
public class deliveryService{
    private Product product = new Product();
    private Movable transportation = null;
    private Movable myShip = new Ship();
    private Movable myTruck = new Truck();

    public void shiftTransportation(Way to){//Strategy Pattern
        if(to == Way.SHIP){
            transportation = myShip;
        }else if(to == Way.TRUCK) {
            transportation = myTruck;
        }
    }

    public void deliver(Place destination){
        transportation.load(product);
        transportation.deliver(destination);
    }
}
```
<br/>

### __Pure Fabrication(순수 조립)__
``` A pure fabrication is a class that does not represent a concept in the problem domain, specially made up to achieve low coupling, high cohesion, and the reuse potential thereof derived (when a solution presented by the information expert pattern does not). ```
+ This kind of class is called a "service" in domain-driven design.
<br/>

### __Indirection__
``` Use an Mediator Pattern to avoid direct connection of two objects ```
```java
public class BulletsManager{// Mediator
    private List<Bullet> bullets;
    private List<int> availableBulletIdxList;

    public void shoot(int speed){
        if(availableBulletIdxList.size() > 0){
            Bullet bullet = bullets.get(availableBulletIdxList.get(0));
            
            if(bullet.state == BulletState.AVAILABLE){
                availableBulletIdxList.remove(bullet);
                bullet.state = BulletState.FIRED;
                bullet.fly(speed);
            }
        }
    }
}
public class BattleShip{
    private BulletsManager bulletsManager;
    private int shootingSpeed;
    
    public shootBullet(){
        bulletsManager.shoot(shootingSpeed);
    }
}
```
<br/>

### __Protected Variations__
``` Anticipate and classify unstable or changeable elements, and assign responsibilities to have a stable interface. ```
<br/>