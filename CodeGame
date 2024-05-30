# Импортируем нужный нам модуль
import random


# Возращает список цифр числа
def getDigits(num):
    return [int(i) for i in str(num)]


# Возращает true, если число без повторяющихся цифр
def noDuplicates(num):
    num_li = getDigits(num)
    if len(num_li) == len(set(num_li)):
        return True
    else:
        return False


# Генератор 4-значного числа без повторяющихся цифр
def generateNum():
    while True:
        num = random.randint(1000, 9999)
        if noDuplicates(num):
            return num

        # возращает общии цифры с точным


# Быки и коровы
def numOfBullsCows(num, guess):
    bull_cow = [0, 0]
    num_li = getDigits(num)
    guess_li = getDigits(guess)

    for i, j in zip(num_li, guess_li):

        # нет совпадения цифр
        if j in num_li:

            # совпадение цифр
            if j == i:
                bull_cow[0] += 1

            # совпадение цифр, но неправильное положение
            else:
                bull_cow[1] += 1

    return bull_cow



num = generateNum()
tries = int(input('Введите количество попыток: '))

# Игра пока правильно не угадано или пока попытки не закончились
while tries > 0:
    guess = int(input("Ваша попытка: "))

    if not noDuplicates(guess):
        print("Число должно быть без повторяющихся цифр. Попробуйте ещё раз.")
        continue
    if guess < 1000 or guess > 9999:
        print("Вводить можно только 4-значное число. Попробуйте ещё раз.")
        continue

    bull_cow = numOfBullsCows(num, guess)
    print(f"быков: {bull_cow[0]} , коров: {bull_cow[1]} ")
    tries -= 1

    if bull_cow[0] == 4:
        print("Число отгадано!")
        break
else:
    print(f"Ваши попытки истекли. Загаданое число было {num}")
