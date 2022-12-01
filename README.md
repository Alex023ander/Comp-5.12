# Comp-5.12
Uses text file to create golf scores and determine who won


import java.io.*;
import java.util.*;
public class Comp512 {

    
    public static void main(String[] args) throws FileNotFoundException {
        final int HOLES = 28, VALUES_PER_LINE = 4;

         int hole = 0;
         int parscores[] = new int[HOLES];
         //declare a file object to handle the text file with scores
         File file1 = new File("D:/Alex0/Documents/golf.txt");
         
         int sum0=0;

         int sum1=0;

         int sum2=0;

         int sum3=0;

         int sum4=0;

         Scanner scan = new Scanner(file1);

         // total par and scores for all holes

         int scores[][] = new int[HOLES][VALUES_PER_LINE];

         //loop to store the contents of the file into arrays

         while (scan.hasNext())
         {
             int index = 0;

             parscores[hole] = scan.nextInt();

                  while (index < 4)
             {
                  scores[hole][index] = scan.nextInt();        // values in a line
                  index++;
             }
             hole++;
         }
         for(int i=0;i<HOLES;i++)
         {
            sum0+=parscores[i];
         }
         
         int sumarray[]=new int[4];
         //loop to calculate the total score of each player
         for(int row=0;row<HOLES;row++)
         {
            sum1+=scores[row][0];
             
            sum2+=scores[row][1];
             
            sum3+=scores[row][2];

             sum4+=scores[row][3];  
         }

         System.out.println();

         System.out.println("Par for the course "+sum0);

         System.out.println("Player 1:"+sum1);

         System.out.println("Player 2:"+sum2);

         System.out.println("Player 3:"+sum3);

         System.out.println("Player 4:"+sum4);

         sumarray[0]=sum1;

         sumarray[1]=sum2;

         sumarray[2]=sum3;

         sumarray[3]=sum4;

         int min=sumarray[0];

         //Loop to find out the minimum score

         for(int j=0;j<4;j++)

         {

             if(sumarray[j]<min)

                  min=sumarray[j];
         }

         System.out.print("The winner is ");

         //condition statement to determine the winner

         if(min==sum1)
         {
             System.out.print("Player1");
         }

             else if(min==sum2)
             {
                  System.out.print("Player2");
         }
             else if(min==sum3)
             {
                  System.out.print("Player3");
         }
             else
             {
                  System.out.print("Player4");
         }

    }


}




//text file golf.txt
1 2 3 4 5
3 5 1 6 7
4 2 3 1 5
4 3 2 5 1
1 3 2 4 5
4 2 5 1 6
7 4 6 3 1
5 1 3 4 2
4 1 3 6 2
4 2 6 4 1
4 2 6 3 5
1 5 3 2 5
5 2 4 7 4
1 4 2 6 3
6 2 5 1 4
2 5 1 4 6
5 6 2 4 1
