# otus-cpp-basic-hw3

# Игра «угадай число» с таблицей рекордов

Игра «угадай число» - компьютер загадывает число, пользователь пытается угадать.
При этом подсчитывается количество попыток и формируется таблица рекордов.

Суть игры. Приложение «загадывает» некоторое число и ждёт в цикле ввода от пользователя. 
В случае, если пользователь ввёл число, меньшее загаданного, выводится подсказка «less than». 
В случае, если пользователь ввёл число, большее заданного, выводится подсказка «greater than». 
В случае, когда пользователь, наконец, угадывает число, выводится сообщение «you win!», и цикл
ввода завершается.

В качестве "загадывания" используется простой генератор случайных чисел из стандартной библиотеки – std::rand.
Для ограничения диапазона значения загадываемого числа используется параметр max_value.

# Описание.

NAME: 
    guess_the_number - program that simulates the game "guess the number".
    
SYNOPSIS:
    guess_the_number [ -max max_value | -level lvl | -table ]

DESCRIPTION:
    guess_the_number is a game application of "guess the number" game. 
    The program generates a random number using a simple generator from the standard library - std::rand. 
    The program then initiates a dialog session with the user via standard input/output 
    and prompts the user to enter the username. After that, the program prompts the user to enter a number:
    
      1. if the user entered a number less than the generated one, then the program displays the hint "less than";
      2. if the user entered a number greater than the generated one, then the program displays a hint "greater than";
      3. if the user guessed the number, the program displays the message "you win!" and ends the session.
    
    During the game, the program counts the number of attempts and generates a high score table in the file high_scores.txt.
    If in the next game the user has surpassed his record, then the data in the table will be overwritten.
    
    The options are as follows:
    
    -max max_value
                    sets the maximum value limit (max_value) for the hidden number. Default max_value is 100.
                    The parameter max_value can take a value from 0 to the constant RAND_MAX.
    
    -level lvl
                    sets the difficulty level of the game, the lvl parameter can take values 1, 2 and 3:
                      a) 1 - the max value will be set to 10 (the hidden number will be in the range from 0 to 9);
                      b) 2 - the max value will be set to 50 (the hidden number will be in the range from 0 to 49);
                      c) 3 - the max value will be set to 100 (the hidden number will be in the range from 0 to 99).
                 
    -table
                    displays a high score table without the need to play.
  
FILES:
    ./high_scores.txt
                    a file for storing the high score table.
