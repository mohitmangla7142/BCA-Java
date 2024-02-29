1.	Encapsulation is the bundling of data and methods that operate on the data into a single unit, called a class. It hides the internal state of an object from the outside world and only exposes the necessary functionality through well-defined interfaces. 
Create an Employee class having data members' Name, Eid, and Basic_Salary, to calculate the HRA is 20% of Basic Salary and DA is 25% of Basic salary and MA is 300 rupee. implement the following queries:
  a) Display the name and gross salary of an employee whose name starts With 'n'
  b).Display the Eid and gross salary whose Eid is equal to 107.
  c)  Count the total number of employees whose salary more than 20000/-

Ans 1:

import java.util.ArrayList;
import java.util.List;

public class Employee {
    private String name;
    private int eid;
    private double basicSalary;

    
    public Employee(String name, int eid, double basicSalary) {
        this.name = name;
        this.eid = eid;
        this.basicSalary = basicSalary;
    }

    
    public double calculateGrossSalary() {
        double hra = 0.20 * basicSalary;
        double da = 0.25 * basicSalary;
        double ma = 300;

        return basicSalary + hra + da + ma;
    }

    
    public String getName() {
        return name;
    }

    public int getEid() {
        return eid;
    }

    
    public static void main(String[] args) {
        Employee[] employees = {
            new Employee("John", 101, 25000),
            new Employee("Nancy", 102, 18000),
            new Employee("Mike", 103, 30000),
        };

        // a) Display the name and gross salary of an employee whose name starts with 'N'
        System.out.println("Employees whose name starts with 'N':");
        for (Employee employee : employees) {
            if (employee.getName().startsWith("N")) {
                System.out.println("Name: " + employee.getName() + ", Gross Salary: " + employee.calculateGrossSalary());
            }
        }

        // b) Display the Eid and gross salary whose Eid is equal to 107
        int targetEid = 107;
        System.out.println("\nEmployee with Eid " + targetEid + ":");
        for (Employee employee : employees) {
            if (employee.getEid() == targetEid) {
                System.out.println("Eid: " + employee.getEid() + ", Gross Salary: " + employee.calculateGrossSalary());
                break; 
            }
        }

        // c) Count the total number of employees whose salary is more than 20000/-
        int count = 0;
        for (Employee employee : employees) {
            if (employee.calculateGrossSalary() > 20000) {
                count++;
            }
        }
        System.out.println("\nTotal number of employees with salary more than 20000: " + count);
        System.out.println("MohitMangla-2210997142");
    }
    
}
