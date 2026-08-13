# Week-5
Quantity and total price 
import java.util.*;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        ArrayList<Product> products = new ArrayList<>();

        products.add(new Product(1, "Laptop", 55000));
        products.add(new Product(2, "Mobile", 25000));
        products.add(new Product(3, "Headphones", 2000));
        products.add(new Product(4, "Keyboard", 1200));

        double total = 0;

        System.out.println("===== PRODUCTS =====");

        for (Product p : products) {
            p.display();
        }

        System.out.print("\nEnter Product ID: ");
        int id = sc.nextInt();

        System.out.print("Enter Quantity: ");
        int quantity = sc.nextInt();

        boolean found = false;

        for (Product p : products) {

            if (p.id == id) {

                double amount = p.price * quantity;
                total = total + amount;

                System.out.println("\nProduct: " + p.name);
                System.out.println("Quantity: " + quantity);
                System.out.println("Price: Rs." + p.price);
                System.out.println("Total: Rs." + amount);

                found = true;
                break;
            }
        }

        if (!found) {
            System.out.println("Product not found.");
        }

        System.out.println("\nGrand Total: Rs." + total);

        sc.close();
    }
}

class Product {

    int id;
    String name;
    double price;

    Product(int id, String name, double price) {
        this.id = id;
        this.name = name;
        this.price = price;
    }

    void display() {
        System.out.println(
            id + ". " + name + " - Rs." + price
        );
    }
}
