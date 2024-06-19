public class Exercise_13_09 {
    /** Main method */
    public static void main(String[] args) {
        // Create three Circle objects
        Circle circle1 = new Circle(5, "red", true);
        Circle circle2 = new Circle(5, "green", false);
        Circle circle3 = new Circle(4, "green", false);

        //  results
        System.out.println("Circle1 radius: " + circle1.getRadius());
        System.out.println("Circle2 radius: " + circle2.getRadius());
        System.out.println("Circle3 radius: " + circle3.getRadius());

        System.out.println("Circle1 is " + (circle1.equals(circle2) ? "" : "not ") +
            "equal to Circle2");

        System.out.println("Circle1 is " + (circle1.equals(circle3) ? "" : "not ") +
            "equal to Circle3");
    }
}

class GeometricObject {
    // Assuming the GeometricObject class has these attributes and methods
    private String color = "white";
    private boolean filled;
    private java.util.Date dateCreated;

    //  constructor
    public GeometricObject() {
        dateCreated = new java.util.Date();
    }

    // Parameterized constructor
    public GeometricObject(String color, boolean filled) {
        dateCreated = new java.util.Date();
        this.color = color;
        this.filled = filled;
    }


    public String getColor() {
        return color;
    }

    public void setColor(String color) {
        this.color = color;
    }

    public boolean isFilled() {
        return filled;
    }

    public void setFilled(boolean filled) {
        this.filled = filled;
    }

    public java.util.Date getDateCreated() {
        return dateCreated;
    }

    
    public String toString() {
        return "created on " + dateCreated + "\ncolor: " + color + " and filled: " + filled;
    }
}

class Circle extends GeometricObject implements Comparable<Circle> {
    private double radius;

    //  constructor
    public Circle() {
    }

    //  constructor
    public Circle(double radius) {
        this.radius = radius;
    }

    // Parameterized constructor with color and filled
    public Circle(double radius, String color, boolean filled) {
        super(color, filled);
        this.radius = radius;
    }

    // Getters and setters
    public double getRadius() {
        return radius;
    }

    public void setRadius(double radius) {
        this.radius = radius;
    }

    // Calculate area
    public double getArea() {
        return Math.PI * radius * radius;
    }

    // Calculate perimeter
    public double getPerimeter() {
        return 2 * Math.PI * radius;
    }

    // Calculate diameter
    public double getDiameter() {
        return 2 * radius;
    }

  
    @Override
    public int compareTo(Circle o) {
        if (this.radius > o.radius) {
            return 1;
        } else if (this.radius < o.radius) {
            return -1;
        } else {
            return 0;
        }
    }

    // Override equals method from Object class
    @Override
    public boolean equals(Object obj) {
        if (this == obj) {
            return true;
        }
        if (obj instanceof Circle) {
            Circle other = (Circle) obj;
            return this.radius == other.radius;
        }
        return false;
    }

    // Override toString method
    @Override
    public String toString() {
        return super.toString() + "\nradius: " + radius;
    }
}
