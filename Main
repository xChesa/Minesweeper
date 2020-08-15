package minesweeper;

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        boolean validEntry;
        int numMines;
        int boardWidth;
        int boardHeight;
        do {
            System.out.println("What size board would you like to play on? (width x height)");
            boardWidth = scan.nextInt();
            boardHeight = Integer.parseInt(scan.nextLine().trim());

            System.out.print("How many mines do you want on the field? ");
            numMines = Integer.parseInt(scan.nextLine().trim());
            validEntry = boardWidth * boardHeight > numMines;
        } while (!validEntry);

        Minesweeper minesweeper = new Minesweeper(boardWidth, boardHeight, numMines);

        while (!minesweeper.isGameOver()) {
            System.out.print("Set/unset mines marks or claim a cell as free: ");
            String[] input = scan.nextLine().split(" ");
            int x = Integer.parseInt(input[0]);
            int y = Integer.parseInt(input[1]);
            String command = input[2].toLowerCase();
            switch (command) {
                case "free":
                    if (minesweeper.doMove(y, x)) {
                        minesweeper.printBoard();
                    }
                    break;
                case "mine":
                    if (minesweeper.placeFlag(y, x)) {
                        minesweeper.printBoard();
                    }
                    break;
            }
        }
        if (minesweeper.isPlayerWin()) {
            System.out.println("Congratulations! You found all mines!");
        } else {
            System.out.println("You stepped on a mine and failed!");
        }
    }
}
