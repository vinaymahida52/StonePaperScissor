# StonePaperScissor
This is a amazing Game which you might have played in your past or at present also. The name of the game is Stone Paper Scissor in which there are two players where first is user i.e. you yourself and the second player is the computer. In this game you have to select any of the three things from stone paper scissors. If the computer has stone and you have paper then you will win and vice-versa cause a paper can wrap the stone , if computer has scissor and you have paper then you will lose and vice-versa cause scissor can easily cut the paper, if computer chose stone and you chose stone then computer will win and vice-versa cause stone can easily damage the scissor, if you and computer chose the same the match will be tie. This game has 10 rounds and at the end you will get the result with the points you and computer scored. Hope you will enjoy the game. 



****************************************************************************************************************************************************************************

        #include <stdio.h>
        #include <stdlib.h>
        #include <time.h>

        int rockpaperscissor(char comp, char player)

        {
            int result;
            // draw conditions
            // rr
            // pp
            // ss
            if (comp == player)
            {
                return result = 0;
            }
            // non draw condiition
            // rp pr
            // rs sr
            // ps sp
            if (comp == 'r' && player == 'p')
            {
                return result = 1;
            }
            else if (comp == 'p' && player == 'r')
            {
                return result = -1;
            }

            if (comp == 'r' && player == 's')
            {
                return result = -1;
            }
            else if (comp == 's' && player == 'r')
            {
                return result = 1;
            }

            if (comp == 'p' && player == 's')
            {
                return result = 1;
            }
            else if (comp == 's' && player == 'p')
            {
                return result = -1;
            }
        }

        int main()
        {
            char user, computer;
            int num;
            int result;
            int comp_ans = 0;
            int user_ans = 0;

            printf("Lets play ROCK PAPER SCISSOR\n");
            printf("You can select the option by their first initial\n");
            printf("For example:-\n");
            printf("Rock = 'r'\n");
            printf("Paper = 'p'\n");
            printf("Scissor = 's'\n");
            printf("Let's start please select from rock, paper, scissor.\n");

            for (int i = 0; i <= 10; i++)
            {
                printf("Roooock Papeeer Scisooor\n");
                fflush(stdin);
                scanf("%c", &user);

                srand(time(0));
                num = rand() % 3 + 1;

                if (num == 1)
                {
                    computer = 'r';
                }
                else if (num == 2)
                {
                    computer = 'p';
                }
                else
                {
                    computer = 's';
                }

                if (user != 'r' && user != 'p' && user != 's')
                {
                    printf("Unidentified input, please try again\n");
                    break;
                }

                if (user == 'r' || user == 'p' || user == 's')
                {
                    printf("You have selected %c and computer has selected %c\n", user, computer);
                }

                result = rockpaperscissor(computer, user);
                if (result == 0)
                {
                    printf("This is tie\n");
                }

                else if (result == -1)
                {
                    printf("You lose\n");
                    comp_ans++;
                    user_ans--;
                }
                else if (result == 1)
                {
                    printf("You win\n");
                    comp_ans--;
                    user_ans++;
                }
            }

            if (user == 'r' || user == 'p' || user == 's')
            {
            if (user_ans > comp_ans)
            {
                printf("Your total score is %d and computer total score is %d\n", user_ans, comp_ans);
                printf("Congratulations, You win\n");
                printf("See you in the next game\n");
            }
            else if (comp_ans > user_ans)
            {
                printf("Your total score is %d and computer total score is %d\n", user_ans, comp_ans);
                printf("Computer won the game\n");
                printf("Better luck next time\n");
            }
            else if (comp_ans == user_ans)
            {
                printf("Your total score is %d and computer total score is %d\n", user_ans, comp_ans);
                printf("The match is tie\n");
                printf("It was a tough competition, will play again to see who wins\n");
            }
            }

            return 0;
        }
