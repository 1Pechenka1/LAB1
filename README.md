# LAB1
# Значения a и n вводить через пробел
def findNOD(a, b):
    if b == 0:
        return a, 1, 0
    else:
        nod, x1, y1 = findNOD(b, a % b)
        x = y1
        y = x1 - (a // b) * y1
        print("x1 =", x)
        return nod, x, y

def findObr(a, n):
    nod, x, y = findNOD(a, n)
    if nod != 1:
        return 0
    else:
        return x % n

a, n = map(int, input("Введите значения a и n -> ").split())

obrat = findObr(a, n)

print("Обратный элемент к числу a по модулю n =", obrat)
