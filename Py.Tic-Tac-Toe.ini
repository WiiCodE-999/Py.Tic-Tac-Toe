def print_board(board):
    for row in board:
        print('|'.join(row))
        print('-' * 5)

def check_win(board, player):
    # Проверка строк
    for row in board:
        if all(cell == player for cell in row):
            return True

    # Проверка столбцов
    for col in range(3):
        if all(board[row][col] == player for row in range(3)):
            return True

    # Проверка диагоналей
    if all(board[i][i] == player for i in range(3)) or \
       all(board[i][2-i] == player for i in range(3)):
        return True

    return False

def check_draw(board):
    for row in board:
        if ' ' in row:
            return False
    return True

def main():
    board = [[' ' for _ in range(3)] for _ in range(3)]
    current_player = 'X'

    while True:
        print_board(board)
        print(f"Ход игрока {current_player}")

        while True:
            try:
                row = int(input("Введите ряд (1-3): ")) - 1
                col = int(input("Введите колонку (1-3): ")) - 1

                if 0 <= row <= 2 and 0 <= col <= 2:
                    if board[row][col] == ' ':
                        break
                    else:
                        print("Эта ячейка уже занята!")
                else:
                    print("Числа должны быть от 1 до 3!")
            except ValueError:
                print("Пожалуйста, введите числа!")

        board[row][col] = current_player

        if check_win(board, current_player):
            print_board(board)
            print(f"Игрок {current_player} победил!")
            break

        if check_draw(board):
            print_board(board)
            print("Ничья!")
            break

        current_player = 'O' if current_player == 'X' else 'X'

if __name__ == "__main__":
    main()