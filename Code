package com.landlord.dashboard;

import java.util.ArrayList;
import java.util.Scanner;

class Property {
    String address;
    double rent;
    boolean occupied;

    Property(String address, double rent, boolean occupied) {
        this.address = address;
        this.rent = rent;
        this.occupied = occupied;
    }
}

public class LandlordDashboard {

    static ArrayList<Property> properties = new ArrayList<>();
    static Scanner sc = new Scanner(System.in);

    public static void main(String[] args) {

        int choice;

        do {
            System.out.println("\n----- LANDLORD DASHBOARD -----");
            System.out.println("1. Add Property");
            System.out.println("2. View Properties");
            System.out.println("3. Dashboard Summary");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");

            choice = sc.nextInt();
            sc.nextLine(); // consume newline

            switch (choice) {
                case 1:
                    addProperty();
                    break;

                case 2:
                    viewProperties();
                    break;

                case 3:
                    showDashboard();
                    break;

                case 4:
                    System.out.println("Exiting program...");
                    break;

                default:
                    System.out.println("Invalid choice!");
            }

        } while (choice != 4);
    }

    static void addProperty() {
        System.out.print("Enter address: ");
        String address = sc.nextLine();

        System.out.print("Enter rent: ");
        double rent = sc.nextDouble();

        System.out.print("Is property occupied? (true/false): ");
        boolean occupied = sc.nextBoolean();
        sc.nextLine(); // consume newline

        Property property = new Property(address, rent, occupied);
        properties.add(property);

        System.out.println("Property added successfully!");
    }

    static void viewProperties() {

        if (properties.isEmpty()) {
            System.out.println("No properties available.");
            return;
        }

        System.out.println("\n--- Property List ---");

        for (int i = 0; i < properties.size(); i++) {
            Property p = properties.get(i);

            System.out.println("Property " + (i + 1));
            System.out.println("Address: " + p.address);
            System.out.println("Rent: " + p.rent);
            System.out.println("Occupied: " + p.occupied);
            System.out.println("----------------------");
        }
    }

    static void showDashboard() {

        int total = properties.size();
        int occupiedCount = 0;
        double totalRent = 0;

        for (Property p : properties) {
            if (p.occupied) {
                occupiedCount++;
            }
            totalRent += p.rent;
        }

        int vacant = total - occupiedCount;

        System.out.println("\n--- Dashboard Summary ---");
        System.out.println("Total Properties: " + total);
        System.out.println("Occupied: " + occupiedCount);
        System.out.println("Vacant: " + vacant);
        System.out.println("Total Rent Income: " + totalRent);
    }
}
