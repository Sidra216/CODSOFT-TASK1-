# CODSOFT
import java.util.Scanner;
class Game
{
    int x,y,score; String name;
    Game()
    {
        score=x=y=0;
    }
            void guess()
            {
                Scanner sc=new Scanner(System.in);
                System.out.println("guess a number between 10 to 99");
                y=sc.nextInt();
            }
            void generate()
            {
                x=(int)(Math.random()*(99-10)+10);
            }
            void menu()
            {
                System.out.println("Guess Game");
                Scanner sc=new Scanner(System.in);
                System.out.println("Your Name:");
                name=sc.nextLine();
                System.out.println("Welcome"+name);
                System.out.println("maximum no.of attempt:5");
                System.out.println("START");
            }
            void play()
            {
                menu();
                for(int r=1;r<=3;r++)
                {
                    generate();
                    System.out.println("Round "+r+":");
                    for(int i=1;i<=5;i++)
                    {
                        guess();
                        if(x==y)
                        {
                            System.out.println("Correct Answer!\n Tou Won!!");
                            score=score+10;
                            break;
                        }
                        else if((y>x && y<=x+10)||(y<x && y<=x-10))
                        {
                            System.out.println("You are near to the number");
                        }
                        else if(y>x+10)
                        {
                            System.out.println("Too High");
                        }
                        else
                        {
                        System.out.println("Too Low");
                        }
                    }
                    System.out.println("Your score:"+score);
                    
  }
            }
    public static void main(String args[])
     {
         Game G=new Game();
          G.play();
       }
   }
