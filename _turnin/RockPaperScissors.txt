/*
    Patrick Barnes
    https://github.com/pdbarnesCSUF/isds309_hw3
*/
/*
-----
  8
-----
In the game Rock Paper Scissors, two players simultaneously choose
 one of three options: rock, paper, or scissors. If both players 
 choose the same option, then the result is a tie. However, if 
 they choose differently, the winner is determined as follows:

Rock beats scissors, because a rock can break a pair of scissors.

Scissors beats paper, because scissors can cut paper.

Paper beats rock, because a piece of paper can cover a rock.

Create a game in which the computer randomly chooses rock, paper,
 or scissors. Let the user enter a character, r, p, or s, each 
 representing one of the three choices. Then, determine the winner.
 Save the application as RockPaperScissors.cs.
*/
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using static System.Console;

namespace RockPaperScissors
{
    class RockPaperScissors
    {
        enum Rps { ROCK = 'r', PAPER = 'p', SCISSOR = 's'}
        static void Main(string[] args)
        {
            WriteLine("hw3#8 - Patrick Barnes");
            WriteLine("RockPaperScissors");

            Rps player = Rps.ROCK;
            Rps computer = Rps.ROCK;
            int rand = 0;
            //------------------- rand
            Random ranNumberGenerator = new Random();
            rand = ranNumberGenerator.Next(1, 4);
            if (rand == 1)
                computer = Rps.ROCK;
            else if (rand == 2)
                computer = Rps.PAPER;
            else
                computer = Rps.SCISSOR;
            //WriteLine("DEBUG comp:" + computer); //DEBUG
            //------------------- input
            WriteLine("r,p,or s? :");
            player = (Rps)(ReadLine())[0];
            //WriteLine("DEBUG player:" + player); //DEBUG
            WriteLine("Computer picked " + computer);
            //------------------- victory
            if (computer == player)
                WriteLine("Tie!");
            else if (computer == Rps.ROCK)
            {
                if (player == Rps.PAPER)
                    Write("Player");
                else
                    Write("Computer");
            }
            else if (computer == Rps.PAPER)
            {
                if (player == Rps.SCISSOR)
                    Write("Player");
                else
                    Write("Computer");
            }
            else //computer == Rps.SCISSOR
            {
                if (player == Rps.ROCK)
                    Write("Player");
                else
                    Write("Computer");
            }
            WriteLine(" Wins!");
            WriteLine("--End--");
        }
    }
}
