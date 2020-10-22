package com.codewithyan;

//Code by Yan
//Started: 22/10/2020
//Finished:

import java.io.*;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner info = new Scanner(System.in);
        //Scanner is used so I can get the user Keyboard input.


            //Now, we will get input about the user information.
            System.out.println("Welcome to User File Input information!");
            System.out.println("");

            System.out.println("Let's get it started. What's your first name?");
            String userName = info.nextLine();

            System.out.println("What's your surname?");
            String userSurname = info.nextLine();

            char userGender;
            do {
                System.out.println("Please, specify your gender. Use 'M' for Male, 'F' for Female, and 'T' for Transgender!");
                userGender = info.nextLine().charAt(0);
            } while (userGender != 'M' && userGender != 'F' && userGender != 'T');
            //Do-while was used here, so if the person input any number above 100 will return the question.

            int userAge;
            do {
                System.out.println("How old are you? Make sure that you are younger than 100!");
                userAge = info.nextInt();
            } while (userAge > 100);


            //Now, we are going to set the titles according to the gender.
            String title = "";

            if (userGender == 'M') {
                title = "Mr. ";
            } else if (userGender == 'F') {
                title = "Ms. ";
            } else if (userGender == 'T') {
                title = "Mx. ";
            }


            //Now, we will set the status, according to the age
            String status = "";

            if (userAge <= 18) {
                status = "School";
            }
            if (userAge >= 19) {
                status = "College";
            }
            if (userAge >= 26) {
                status = "Worker";
            }
            if (userAge >= 67) {
                status = "Retired";
            }


        //Now we will create the output file code
        String file = "people.txt";
        try {

            BufferedWriter writer = new BufferedWriter(new FileWriter(file, true));

            //Here was added the user Title, Surname, name and Status
            writer.write(title);
            writer.write(userSurname+",");
            writer.write(" " + userName.charAt(0));

            writer.newLine();

            writer.write(status);
            writer.newLine();

            writer.close();

        } catch (Exception e) {

        }








    }
}
