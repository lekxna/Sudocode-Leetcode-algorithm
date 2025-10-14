# Sudocode-Leetcode-algorithm
leet code algorothm that is sudoku
using System;

namespace sudo_k
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Random rand = new Random();
            int Num = rand.Next(1, 10);

            int[,] sudokuboard = new int[9, 9]
            {
                {5,3,0,0,7,0,0,0,0},
                {6,0,0,1,9,5,0,0,0},
                {0,9,8,0,0,0,0,6,0},
                {8,0,0,0,6,0,0,0,3},
                {4,0,0,8,0,3,0,0,1},
                {7,0,0,0,2,0,0,0,6},
                {0,6,0,0,0,0,2,8,0},
                {0,0,0,4,1,9,0,0,5},
                {0,0,0,0,8,0,0,7,9}
            };

            int alreadyin = 0;
            int n = 0;
            int z = 0;
            int numberchance = 0;

            for (int row = n; row < 3; row++)
            {
                for (int col = z; col < 3; col++)
                {
                    
                    Num = rand.Next(1, 10);

                    
                    if (sudokuboard[row, col] == 0)
                    {
                        sudokuboard[row, col] = Num;
                    }
                }

                if (row % 3 == 0 && row != 0)
                {
                    for (int i = 0; i < 9; i++)
                    {
                        for (int j = 0; j < 3; j++)
                        {
                            for (int k = 0; k < 3; k++)
                            {
                                if (Num != sudokuboard[z + j, n + k])
                                {
                                    alreadyin = 1;
                                    Num++;
                                    if (Num > 9)
                                    {
                                        Num = 1;
                                    }
                                }
                            }
                        }
                    }
                }
            }

            Console.WriteLine("Sudoku Board:");
            for (int i = 0; i < 9; i++)
            {
                for (int j = 0; j < 9; j++)
                {
                    Console.Write(sudokuboard[i, j] + " ");
                }
                Console.WriteLine();
            }

            Console.ReadKey();
        }
    }
}
