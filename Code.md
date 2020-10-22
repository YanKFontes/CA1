package com.codewithyan;

//Code by Yan
//22/10/2020

import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner userInfo = new Scanner(System.in);

        System.out.println("Hello, welcome to the User Input information!");
        System.out.println("What's your First name?");
        String userName = userInfo.nextLine();

        System.out.println("What's your surname?");
        String userSurname = userInfo.nextLine();

        System.out.println("Can you specify your gender? M for Male, F for Female, and T for Transgender");
        char userGender = userInfo.next().charAt(0);

        System.out.println("How old are you?");
        int userAge = userInfo.nextInt();

        if (userAge > 100) {
            System.out.println("You should be younger than 100 years old!");
        }

        String title = "";

        if (userGender == 'M') {
            title = "Mr ";
        } else if (userGender == 'F') {
            title = "Ms ";
        } else if (userGender == 'T') {
            title = "Mx ";
        } else {
            System.out.println("Your gender was tipped wrong!");
        }

        String userStatus ="";

        if (userAge <= 18) {
            userStatus = "School"; }

        if (userAge >= 19) {
            userStatus = "College"; }

        if (userAge >= 26) {
            userStatus = "Worker"; }
        if (userAge >=67) {
            userStatus = "Retired"; }

        String status = "status.txt";

        try {

            BufferedWriter writer = new BufferedWriter(new FileWriter(status, true));

            writer.write(title);
            writer.write(userSurname+',');
            writer.write(" " + userName.charAt(0));

            writer.newLine();

            writer.write(userGender);

            writer.newLine();

            writer.write(userStatus);

            writer.newLine();

            writer.close();



        } catch (IOException e) {
            System.out.println("File not found!");
        }





    }
}
