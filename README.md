# available_password
from random import *
digits = '123456789'
lowercase_letters = 'abcdefghijklmnopqrstuvwxyz'
uppercase_letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
punctuation = '!#$%&*+-=?@^_'
print('Укажите колличество паролей для генерации')
quantity = int(input())
print('Укажите длину пароля')
lenth = int(input())

def set_of_chars():
    alchars = ''
    print('Включать цифры: да/нет ?')
    cifri = input()
    if cifri.lower() == 'да':
        alchars += digits
    print('Включать ли прописные буквы? да/нет')
    propisi = input()
    if propisi.lower() == 'да':
        alchars += lowercase_letters
    print('Включать ли строчные буквы? да/нет')
    stroki = input()
    if stroki.lower() == 'да':
        alchars += uppercase_letters
    print('Включать ли символы? да/нет')
    simvoli = input()
    if simvoli.lower() == 'да':
        alchars += punctuation
    print("Исключать однозначные символы 'il1Lo0O'? да/нет")
    isklyucheniye = input()
    if isklyucheniye.lower() == 'да':
        badsu = "il1Lo0O"
        for i in range(len(badsu)):
            if badsu[i] in alchars:
                alchars.replace(badsu[i], ' ')
    return alchars
def generate_pass(string):
    chars = ''
    for _ in range(lenth):
        chars += choice(string)
    return chars
for _ in range(quantity):
    print(generate_pass(set_of_chars()))


