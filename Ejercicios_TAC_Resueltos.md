# Resolución de ejercicios: Código de Tres Direcciones (TAC)

## Ejercicio 1
**Código Original:**
```text
resultado = (a + b) * c - (d / e)
```

**Código TAC:**
```text
t1 = a + b
t2 = d / e
t3 = t1 * c
t4 = t3 - t2
resultado = t4
```

---

## Ejercicio 2
**Código Original:**
```text
x = ((a * b) + (c - d)) / (e + f)
```

**Código TAC:**
```text
t1 = a * b
t2 = c - d
t3 = t1 + t2
t4 = e + f
t5 = t3 / t4
x = t5
```

---

## Ejercicio 3
**Código Original:**
```text
condicion = (a >= b) && (c < d) || (e == f)
```

**Código TAC:**
```text
t1 = a > b
t2 = a == b
t3 = t1 || t2
t4 = c < d
t5 = e == f
t6 = t3 && t4
t7 = t6 || t5
condicion = t7
```

---

## Ejercicio 4
**Código Original:**
```text
total = (a % b) % (c + d) - (e / f) * g
```

**Código TAC:**
```text
t1 = a % b
t2 = c + d
t3 = e / f
t4 = t1 % t2
t5 = t3 * g
t6 = t4 - t5
total = t6
```

---

## Ejercicio 5
**Código Original:**
```text
valor = (a + b * c - d + e * f) / g
```

**Código TAC:**
```text
t1 = b * c
t2 = e * f
t3 = a + t1
t4 = t3 - d
t5 = t4 + t2
t6 = t5 / g
valor = t6
```

---

## Ejercicio 6
**Código Original:**
```text
x = 9 + 4 * 5 - 3 + 2 + 1 - 5 - 1 * 3
```

**Código TAC:**
```text
t1 = 4 * 5
t2 = 1 * 3
t3 = 9 + t1
t4 = t3 - 3
t5 = t4 + 2
t6 = t5 + 1
t7 = t6 - 5
t8 = t7 - t2
x = t8
```

---

## Ejercicio 7
**Código Original (Python):**
```python
x = 3
y = 5
z = 7
resultado = 2 * x ** 3 + 3 * y ** 2- z + 4 * x * y
```

**Código TAC:**
```text
x = 3
y = 5
z = 7
t1 = x ** 3
t2 = 2 * t1
t3 = y ** 2
t4 = 3 * t3
t5 = t2 + t4
t6 = t5 - z
t7 = 4 * x
t8 = t7 * y
t9 = t6 + t8
resultado = t9
```

---

## Ejercicio 8
**Código Original:**
```javascript
if (x > 0) {
  y = x;
} else {
  y = -x;
}
```

**Código TAC:**
```text
t1 = x > 0
IfZ t1 Goto L1
y = x
Goto L2
L1:
y = - x
L2:
End
```

---

## Ejercicio 9
**Código Original (Python):**
```python
i = 0
while i < 10:
  print(i)
  i = i + 1
```

**Código TAC:**
```text
i = 0
L1:
t1 = i < 10
IfZ t1 Goto L2
PushParam i
LCall _PrintInt
PopParams 4
t2 = i + 1
i = t2
Goto L1
L2:
End
```

---

## Ejercicio 10
**Código Original (PHP):**
```php
function suma($a, $b) {
  return $a + $b;
}
$r = suma(5, 3);
```

**Código TAC:**
```text
suma:
BeginFunc
t1 = a + b
Return t1
EndFunc
main:
BeginFunc
PushParam 3
PushParam 5
t2 = LCall suma
PopParams 8
r = t2
EndFunc
```

---

## Ejercicio 11
**Código Original (Java):**
```java
int a = 5, b = 10;
if (a * 2 > b) {
  b = b - a;
} else {
  b = b + a;
}
```

**Código TAC:**
```text
a = 5
b = 10
t1 = a * 2
t2 = t1 > b
IfZ t2 Goto L1
t3 = b - a
b = t3
Goto L2
L1:
t4 = b + a
b = t4
L2:
End
```

---

## Ejercicio 12
**Código Original (Python):**
```python
name = "Dracula"
age = 500
is_vampire = False
if name == "dracula" or age > 100:
  is_vampire = True
if is_vampire:
  print("Warning! Vampire detected!")
else:
  print("Phew! No vampires here")
```

**Código TAC:**
```text
name = "Dracula"
age = 500
is_vampire = 0
t1 = name == "dracula"
t2 = age > 100
t3 = t1 || t2
IfZ t3 Goto L1
is_vampire = 1
L1:
IfZ is_vampire Goto L2
PushParam "Warning! Vampire detected!"
LCall _PrintString
PopParams 4
Goto L3
L2:
PushParam "Phew! No vampires here"
LCall _PrintString
PopParams 4
L3:
End
```

---

## Ejercicio 13
**Código Original (Python):**
```python
aliens = 5
potencia_laser = 10
if aliens < 10:
  print("¡Aparece una nave nodriza!")
if aliens < 5:
  print("¡Aparece una horda de aliens pequeños!")
if potencia_laser >= aliens * 2:
  print("¡Has ganado el juego!")
else:
  print("Quedan " + str(aliens) + " aliens enemigos.")
```

**Código TAC:**
```text
aliens = 5
potencia_laser = 10
t1 = aliens < 10
IfZ t1 Goto L1
PushParam "¡Aparece una nave nodriza!"
LCall _PrintString
PopParams 4
L1:
t2 = aliens < 5
IfZ t2 Goto L2
PushParam "¡Aparece una horda de aliens pequeños!"
LCall _PrintString
PopParams 4
L2:
t3 = aliens * 2
t4 = potencia_laser > t3
t5 = potencia_laser == t3
t6 = t4 || t5
IfZ t6 Goto L3
PushParam "¡Has ganado el juego!"
LCall _PrintString
PopParams 4
Goto L4
L3:
t7 = "Quedan " + aliens
t8 = t7 + " aliens enemigos."
PushParam t8
LCall _PrintString
PopParams 4
L4:
End
```

---

## Ejercicio 14
**Código Original (Java):**
```java
int shield = 100;
int hits = 0;
while (shield > 0) {
  hits++;
  if (hits == 3) {
    shield = 50;
  }
  shield -= 20;
}
System.out.println("Escudo destruido!");
```

**Código TAC:**
```text
shield = 100
hits = 0
L1:
t1 = shield > 0
IfZ t1 Goto L2
t2 = hits + 1
hits = t2
t3 = hits == 3
IfZ t3 Goto L3
shield = 50
L3:
t4 = shield - 20
shield = t4
Goto L1
L2:
PushParam "Escudo destruido!"
LCall _PrintString
PopParams 4
End
```

---

## Ejercicio 16
**Código Original (C):**
```c
int suma(int a, int b) {
  return a + b;
}
void main() {
  int c;
  int d;
  suma(c, d);
}
```

**Código TAC:**
```text
suma:
BeginFunc
t1 = a + b
Return t1
EndFunc
main:
BeginFunc
PushParam d
PushParam c
LCall suma
PopParams 8
EndFunc
```

---

## Ejercicio 17
**Código Original (Python):**
```python
def usd_a_mxn(usd):
  return usd * 18.50
def mxn_a_usd(mxn):
  return mxn / 18.50
usd = 100
print(usd_a_mxn(usd))
mxn = 10000
print(mxn_a_usd(mxn))
```

**Código TAC:**
```text
usd_a_mxn:
BeginFunc
t1 = usd * 18.50
Return t1
EndFunc
mxn_a_usd:
BeginFunc
t1 = mxn / 18.50
Return t1
EndFunc
main:
BeginFunc
usd = 100
PushParam usd
t2 = LCall usd_a_mxn
PopParams 4
PushParam t2
LCall _PrintInt
PopParams 4
mxn = 10000
PushParam mxn
t3 = LCall mxn_a_usd
PopParams 4
PushParam t3
LCall _PrintInt
PopParams 4
EndFunc
```

---

## Ejercicio 18
**Código Original (C):**
```c
int es_par(int numero) {
  return numero % 2 == 0;
}
int main() {
  int num = 7;
  if (es_par(num)) {
    printf("%d es par\n", num);
  } else {
    printf("%d es impar\n", num);
  }
  return 0;
}
```

**Código TAC:**
```text
es_par:
BeginFunc
t1 = numero % 2
t2 = t1 == 0
Return t2
EndFunc
main:
BeginFunc
num = 7
PushParam num
t3 = LCall es_par
PopParams 4
IfZ t3 Goto L1
t4 = num + " es par\n"
PushParam t4
LCall _PrintString
PopParams 4
Goto L2
L1:
t5 = num + " es impar\n"
PushParam t5
LCall _PrintString
PopParams 4
L2:
Return 0
EndFunc
```

---

## Ejercicio 19
**Código Original (PHP):**
```php
$energy = 80;
$attacks = 0;
while ($energy > 0) {
  if ($attacks >= 2) {
    $energy += 10;
  }
  $energy -= 15;
  $attacks++;
}
echo "Energía agotada!";
```

**Código TAC:**
```text
energy = 80
attacks = 0
L1:
t1 = energy > 0
IfZ t1 Goto L2
t2 = attacks > 2
t3 = attacks == 2
t4 = t2 || t3
IfZ t4 Goto L3
t5 = energy + 10
energy = t5
L3:
t6 = energy - 15
energy = t6
t7 = attacks + 1
attacks = t7
Goto L1
L2:
PushParam "Energía agotada!"
LCall _PrintString
PopParams 4
End
```

---

## Ejercicio 20
**Código Original (Python):**
```python
charge = 0
special_ready = False
while not special_ready:
  charge += 15
  if charge >= 100:
    special_ready = True
  else:
    charge += 5
print("¡Habilidad especial lista!")
```

**Código TAC:**
```text
charge = 0
special_ready = 0
L1:
t1 = special_ready == 0
IfZ t1 Goto L2
t2 = charge + 15
charge = t2
t3 = charge > 100
t4 = charge == 100
t5 = t3 || t4
IfZ t5 Goto L3
special_ready = 1
Goto L1
L3:
t6 = charge + 5
charge = t6
Goto L1
L2:
PushParam "¡Habilidad especial lista!"
LCall _PrintString
PopParams 4
End
```
