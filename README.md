package com.example.Battle;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class Battle {

    public static void main(String[] args) throws IOException {

        int size = choosesize();
        Table table = new Table(size);
        table.InitArray();
        for (int i = 0; i < size; i++) {

            shipPlacement();

            table.setShip();

        }
    }

    //to get size of board with checking for correct number
    private static int choosesize() throws IOException {
        int fieldsize = 0;
        boolean start = true;
        while (start)
            try {
                print("Choose field size (3, 4 or 5):");
                fieldsize = Integer.parseInt(input.readLine());
                if (fieldsize != 3) {
                    if (fieldsize != 4) {
                        if (fieldsize != 5) {
                            if (fieldsize==0){
                                System.exit(0);
                            }
                            print("Invalid value. Please, try again or input 0 to quit");
                        } else {
                            start = false;
                        }
                    } else {
                        start = false;
                    }
                }//first if end
                else {
                    start = false;
                }
            }
            catch (Exception e) {
                print("something is wrong!");
            }
        return fieldsize;
    }

    //just get coordinates of one ship
    private static void shipPlacement() throws IOException {

        print("Put your ships. Choose the row(1,2 or 3):");
        Table.shiprow = Integer.parseInt(input.readLine());
        print("Choose column(1,2 or 3):");
        Table.shipcolumn = Integer.parseInt(input.readLine());
    }


    private static void print(String text) {
        System.out.println(text);
    }

    private static BufferedReader input = new BufferedReader(new InputStreamReader(System.in));
}
