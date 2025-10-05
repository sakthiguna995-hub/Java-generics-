package shapes;
class ShapePrinter implements Runnable {
    private String shape;

    public ShapePrinter(String shape) {
        this.shape = shape;
    }
    public void run() {
        for(int i=0; i<3; i++) {
            switch(shape) {
                case "Triangle":
                    System.out.println("  /\\  ");
                    System.out.println(" /  \\ ");
                    System.out.println("/\\");
                    break;
                case "Square":
                    System.out.println(" _____ ");
                    System.out.println("|     |");
                    System.out.println("|_|");
                    break;
                case "Circle":
                    System.out.println("  ___  ");
                    System.out.println(" /   \\ ");
                    System.out.println("|     |");
                    System.out.println(" \\_/ ");
                    break;
            }
            try { Thread.sleep(500); } catch (InterruptedException e) { }
        }
    }
}

public class MultiShapeThreads {
    public static void main(String[] args) {
        Thread t1 = new Thread(new ShapePrinter("Triangle"));
        Thread t2 = new Thread(new ShapePrinter("Square"));
        Thread t3 = new Thread(new ShapePrinter("Circle"));

        t1.start();
        t2.start();
        t3.start();
    }
}