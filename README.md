# Week-4-In-Class-Activity-Part-2


## Project: Baby Name for Both Genders


### Name your program Exercise12_01Extra

### Problem Description:
*12.1 (Name for both genders) Write a program that prompts the user to enter one of the filenames described in Exercise 12.31 and displays the names that are used for both genders in the file. Here is a sample run:*

> < Output >
Enter a file name for baby name ranking: Babynamesranking2001.txt <Enter icon>
69 names used for both genders 
They are Tyler Ryan Christian ...
< End Output >

Submit the following items:

1. Compile and Submit (you must submit the program regardless whether it complete or incomplete, correct or incorrect) 

2. Submit copies of screen shots of sample run from the command prompt.

3. Fill in self-evaluation:  (Write the self-evaluation on the hard copy for the screen shots)

1.	Can your program read data from the files using its URL and store the data in arrays?
2.	Can your program the names for both genders?



import java.util.Scanner;
import java.io.File;

public class Exercise12_01Extra {

    public static void main(String[] args) throws Exception {
        //asking for the users file name 
        Scanner kb = new Scanner(System.in);
        System.out.println(" Enter a file name for baby name ranking: ");
          String filename = kb.next();
          File inputFile= new File(filename);
  
         populateArray();
         commonName();


        //The file names 
        String[][] names2001 = new String[1000][3];
        populateArray("C:/Users/Yngrid Lizbeth/Documents/babynameranking2001.txt", names2001);
        String[][] names2002 = new String[1000][3];
        populateArray("C:/Users/Yngrid Lizbeth/Documents/babynameranking2002.txt", names2002);
        String[][] names2003 = new String[1000][3];
        populateArray("C:/Users/Yngrid Lizbeth/Documents/babynameranking2003.txt", names2003);
        String[][] names2004 = new String[1000][3];
        populateArray("C:/Users/Yngrid Lizbeth/Documents/babynameranking2004.txt", names2004);
        String[][] names2005 = new String[1000][3];
        populateArray("C:/Users/Yngrid Lizbeth/Documents/babynameranking2005.txt", names2005);
        String[][] names2006 = new String[1000][3];
        populateArray("C:/Users/Yngrid Lizbeth/Documents/babynameranking2006.txt", names2006);
        String[][] names2007 = new String[1000][3];
        populateArray("C:/Users/Yngrid Lizbeth/Documents/babynameranking2007.txt", names2007);
        String[][] names2008 = new String[1000][3];
        populateArray("C:/Users/Yngrid Lizbeth/Documents/babynameranking2008.txt", names2008);
        String[][] names2009 = new String[1000][3];
        populateArray("C:/Users/Yngrid Lizbeth/Documents/babynameranking2009.txt", names2009);
        String[][] names2010 = new String[1000][3];
        populateArray("C:/Users/Yngrid Lizbeth/Documents/babynameranking2010.txt", names2010);

        
   
 

    }/// this reads from the arrays of boy and girl

    public static void populateArray(String listURL, String[][] names) throws Exception {
        //reads a file of three columns; 1-1000, male names, and female names, and transcribes it
        //to an array (column 0 is rank, 1 is male names, 2 is female names)
        Scanner input = new Scanner(new File(listURL));
        for (int i = 0; i < 1000; i++) {
            names[i][0] = "" + input.nextInt();
            names[i][1] = input.next();
            names[i][2] = input.next();

        }

    }// This looks for the common names 

    public static void commonName(String[][] name) throws Exception {
        for (int i = 0; i < 1000; i++) {
            for (int j = 0; j < 1000; j++) {
                if (name[i][1] == name[j][2]) {
                    System.out.println("They are" +name[j][2]);
                }
            }
        }
    }

}

