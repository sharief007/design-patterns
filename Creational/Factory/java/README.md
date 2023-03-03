#### Bike interface

```java
public interface Bike {
    int fuelCapacity;
    int mileage;

    int getRange();
}
```

#### Hayabusa class

```java
public class Hayabusa implements Bike {
    public Hayabusa() {
        this.fuelCapacity = 20;
        this.mileage = 15;
    }

    public int getRange() {
        return this.fuelCapacity * this.mileage;
    }
}
```

#### H2 class

``` java
public class H2 implements Bike {
    public H2() {
        this.fuelCapacity = 19;
        this.mileage = 12;
    }
    public int getRange() {
        return this.fuelCapacity * this.mileage;
    }
}
```

#### R1 class

```java
public class R1 implements Bike {
    public R1() {
        this.fuelCapacity = 17;
        this.mileage = 20;
    }
    public int getRange() {
        return this.fuelCapacity * this.mileage;
    }
}
```

### Bike brands

```java
public enum Brand {
    SUZUKI,
    KAWASAKI,
    YAMAHA
}
```

### Factory Implementation

```java
public class BikeFactory {
    public static Bike createBike(Brand brand) {
        switch(brand) {
            case Brand.SUZUKI:
                return new Hayabusa();
            case Brand.YAMAHA:
                return new R1();
            default:
                return new H2(); 
        }
    }
}
```

### Client

```java
public class Client {
    public static void main(String[] args) {
        Bike hayabusa = BikeFactory.createBike(Brand.SUZUKI);

        System.out.println(hayabusa.getRange());
    }
}
```