/*
    Patrick Barnes
    https://github.com/pdbarnesCSUF/isds309_hw3
*/
/*
-----
  9
-----
Create a lottery game application named Lottery. Generate three 
random numbers, each between 1 and 4. Allow the user to guess three
 numbers. Compare each of the user’s guesses to the three random 
 numbers, and display a message that includes the user’s guess, the
 randomly determined three-digit number, and the amount of money the
 user has won as follows:

         Matching Numbers		|Award ($)
--------------------------------|---------
Any one matching				|10
Two matching					|100
Three matching, not in order	|1000
Three matching in exact order	|10,000
No matches						|0

Make certain that your application accommodates repeating digits. 
For example, if a user guesses 1, 2, and 3, and the randomly 
generated digits are 1, 1, and 1, do not give the user credit 
for three correct guesses—just one.
*/
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using static System.Console;

namespace Lottery
{
    class Lottery
    {
        static void Main(string[] args)
        {
            WriteLine("hw3#9 - Patrick Barnes");
            WriteLine("Lottery");

            const int MIN = 1; //incl
            const int MAX = 5; //excl
            int first = 0, second = 0, third = 0;
            int in_1 = 0, in_2 = 0, in_3 = 0;

            Random ranNumberGenerator = new Random();
            first  = ranNumberGenerator.Next(MIN, MAX);
            second = ranNumberGenerator.Next(MIN, MAX);
            third  = ranNumberGenerator.Next(MIN, MAX);

            WriteLine("DEBUG: {0}, {1}, {2}", first, second, third); //DEBUG
            WriteLine("What are your three numbers? (enter after each");
            in_1 = int.Parse(ReadLine());
            in_2 = int.Parse(ReadLine());
            in_3 = int.Parse(ReadLine());

			//this feels cumbersome
			if (in_1 == first)
			{
				if (in_2 == second)
				{
					if (in_3 == third)
					{
						WriteLine("You've won: 10,000");
					}
					else
					{
						WriteLine("You've won: 100");
					}
				}
				else
				{
					if (in_3 == second)
					{
						if (in_2 == third)
						{
							WriteLine("You've won: 1,000");
						}
						else
						{
							WriteLine("You've won: 100");
						}
					}
					else
					{
						WriteLine("You've won: 10");
					}
				}
			}
			else if (in_2 == first)
			{
				if (in_1 == second)
				{
					if (in_3 == third)
					{
						WriteLine("You've won: 1,000");
					}
					else
					{
						WriteLine("You've won: 100");
					}
				}
				else
				{
					if (in_3 == second)
					{
						if (in_1 == third)
						{
							WriteLine("You've won: 1,000");
						}
						else
						{
							WriteLine("You've won: 100");
						}
					}
					else
					{
						WriteLine("You've won: 10");
					}
				}
			}
			else if (in_3 == first)
			{
				if (in_1 == second)
				{
					if (in_3 == third)
					{
						WriteLine("You've won: 1,000");
					}
					else
					{
						WriteLine("You've won: 100");
					}
				}
				else
				{
					if (in_3 == second)
					{
						if (in_1 == third)
						{
							WriteLine("You've won: 1,000");
						}
						else
						{
							WriteLine("You've won: 100");
						}
					}
					else
					{
						WriteLine("You've won: 10");
					}
				}
			}
			else
			{
				WriteLine ("You've won: 0");
			}

            WriteLine("--End--");

        }
    }
}
