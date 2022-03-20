# Caesar
package com.company;

import java.util.Scanner;

public class Main {



    public static void main(String[] args) {


        Scanner keyboard = new Scanner(System.in);
        System.out.println(" Input the message : ");
        String plaintext = keyboard.nextLine();

        System.out.println("What is the shift value for the cipher? ");
        int s = keyboard.nextInt();

        while (s < 1 || s > 25)
        {
            System.out.println("The shift value must be between 1 and 25. Try again: ");
            s = keyboard.nextInt();
        }

        String ciphertext = "";
        char alphabet;
        for(int i=0; i < plaintext.length();i++)
        {
            // Shift one character at a time
            alphabet = plaintext.charAt(i);

            // if alphabet lies between a and z
            if(alphabet >= 'a' && alphabet <= 'z')
            {
                // shift alphabet
                alphabet = (char) (alphabet + s);
                // if shift alphabet greater than 'z'
                if(alphabet > 'z') {
                    // reshift to starting position
                    alphabet = (char) (alphabet+'a'-'z'-1);
                }
                ciphertext = ciphertext + alphabet;
            }

            // if alphabet lies between 'A'and 'Z'
            else if(alphabet >= 'A' && alphabet <= 'Z') {
                // shift alphabet
                alphabet = (char) (alphabet + s);

                // if shift alphabet greater than 'Z'
                if(alphabet > 'Z') {
                    //reshift to starting position
                    alphabet = (char) (alphabet+'A'-'Z'-1);
                }
                ciphertext = ciphertext + alphabet;
            }
            else {
                ciphertext = ciphertext + alphabet;
            }

        }
        System.out.println(" ciphertext : " + ciphertext);
    }
}
