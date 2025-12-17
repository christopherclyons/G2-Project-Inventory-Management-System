# G2-Project-Inventory-Management-System

"Shelf Control"

    A Java-based desktop application designed to help businesses manage product inventory efficiently.
    
        The system allows users to add, update, delete, and search items within inventory records, maintaining clear visibility into stock levels and product details.
        the program will be written based on five differents classes :
        A Java-based desktop application designed to help businesses manage product inventory efficiently.

    The system allows users to add, update, delete, and search items within inventory records, maintaining clear visibility into stock levels and product details.

Inventory class automatically reorders products when stock is low.
Inventory class that predicts future demand for a product.
Inventory class keeps track of expiration dates and removes expired products.
Inventory class to find products by category.
Inventory  class to find products that are missing.

Final_Project
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 */

package com.mycompany.final_project;

/**
 *
 * @author Ksoul
 */
public class Final_Project {

    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
Main
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package Final_Project;


/*
 * Project: Inventory Management
 * Author: Souley
 * Description: Tests the Inventory system.
 */

public class Main {

    public static void main(String[] args) {

        Inventory inventory = new Inventory();

        Product product1 = new Product("LED TV", 200);
        Product product2 = new Product("Mobile", 80);
        Product product3 = new Product("Tablet", 50);

        System.out.println("Add three products in inventory:");
        inventory.addProduct(product1);
        inventory.addProduct(product2);
        inventory.addProduct(product3);

        System.out.println("\nCheck low inventory:");
        inventory.checkLowInventory();

        System.out.println("\nRemove Tablet from the inventory!");
        inventory.removeProduct(product3);

        System.out.println("\nAgain check low inventory:");
        inventory.checkLowInventory();
    }
}
Product
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package Final_Project;
/**
 * Project: Inventory Management
 * Author: Souley
 * Description: Represents a product with a name and quantity.
 */
public class Product {

    // ===== Attributes =====
    private String name;
    private int quantity;

    // ===== Constructors =====

    // Default constructor
    public Product() {
        this.name = "";
        this.quantity = 0;
    }

    // Parameterized constructor
    public Product(String name, int quantity) {
        this.name = name;
        this.quantity = quantity;
    }

    // ===== Getter and Setter Methods =====
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getQuantity() {
        return quantity;
    }

    public void setQuantity(int quantity) {
        this.quantity = quantity;
    }
}
Inventory
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
 package Final_Project;
 import java.util.ArrayList;
/**
 * Project: Inventory Management
 * Author: Souley
 * Description: Manages a collection of Product objects.
 */

public class Inventory {

    // Collection of products
    private ArrayList<Product> products;

    // Constructor
    public Inventory() {
        products = new ArrayList<>();
    }

    // Add a product
    public void addProduct(Product product) {
        products.add(product);
    }

    // Remove a product
    public void removeProduct(Product product) {
        products.remove(product);
    }

    // Check for low inventory
    public void checkLowInventory() {
        for (Product product : products) {
            if (product.getQuantity() <= 100) {
                System.out.println(
                    product.getName() +
                    " is running low on inventory. Current quantity: " +
                    product.getQuantity()
                );
            }
        }
    }
}


                Authors:  Christopher Lyons; Souleymane Abdoul Karimou; Ibrahim Abdulai
