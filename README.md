# BootCamp Core Code
## 1 WEEK
### - DAY 1: Introduccion
### - DAY 2: 
1.	Java language is compiled or interpreted?
The Java language is both compiled and interpreted. The compiler converts the source code that resides in files whose extension is. java, a set of instructions named bytecodes that are stored in a file whose extension is .class
2.	Why are flowcharts important to us as developers?
At the beginning of a project we must pose the problem and represent it with flow diagrams, this allows the best alternative to be analyzed and found for a code and for its debugging.
3.  Create an algorithm to calculate the equivalent of your local currencty to USD
import java.io.*;
public class sin_titulo {
    public static void main(String args[]) throws IOException {
        BufferedReader bufEntrada = new BufferedReader(new InputStreamReader(System.in));
        double d;
        double q;
        q = 0;
        d = 0;
        System.out.println("ingrese la cantidad en quetzales");
        q = Double.parseDouble(bufEntrada.readLine());
        d = q/7.79;
        System.out.println("la cantidad en dolares son"+"--"+d+"Dolares");
    }
}
4.   Anwser to the question: Why is pseudocode helpful?
the pseudocode allows to create a beta version of the code with a non-formal language and thus verify if there is a certain error to solve it in the best way
5.	Create a pseudocode to calculate the aproximated age of a user base on the year they born, (you can define a variable with the actual year if you need it, like for example i could define Y <-- 2022)
![image](https://user-images.githubusercontent.com/52414295/149167806-7ee3097d-4c9f-4c07-8679-f2de2aa003f8.png)


### - DAY 3: 
1.    Translate the year you where born to binary, decimal and hexadecimal
Decimal 1995-------Binario 11111001011------Hexadecimal 7CB
3.    Translate 51966 into hexadecimal and binary
  -           CAFE         --------------- 1100101011111110          
4.    Base on the examples and the guide of the low-level language: 5.1 Create a program to add two numbers given by the user 5.2 Create a program that display your name

.data
pregunta: .asciiz "¿Cuantos numeros ENTEROS quieres sumar?\n"
 cuales: .asciiz "¿Que números son? Introducelos: \n"
 resultado: .asciiz "\n El resultado de la suma es: "
 .text
main:

#pide por pantalla cuantos elementos ENTEROS va a sumar el usuario
 li $v0, 4
 la $a0, pregunta
 syscall

li $v0, 5
 syscall

move $t1, $v0 #v0 guarda el numero de elementos que quiere sumar el usuario
 addi $t0, $zero, 0#initialize counter(aumenta de uno en uno)

#pregunta cuales son
 li $v0, 4
 la $a0, cuales
 jal input #jumps to function that waits all values introduced by user and saves them to stack

jal suma

move $t1, $v1 #$t1 now holds the result

li $v0, 4
 la $a0, resultado
 syscall

li $v0, 1
 move $a0, $t1
 syscall

j exit

suma:#gives result in $v1

move $t8, $ra#saves a ddress of first caller
 addi $t5, $zero, 0#initialize register where the result will be hold
 addi $t0, $zero, 0#counter of loop

loop_suma:

beq $t0, $t1, end_suma

lw $t6, 0($sp)

add $t5, $t5, $t6

addi $sp, $sp, 4#move on to next position of stack
 addi $t0, $t0, 1#counter loop +1
 j loop_suma

end_suma:
 move $v1, $t5
 move $ra, $t8 #give back control to caller
 jr $ra

input:
 move $t9, $ra#Save address of original

loop_input:

beq $t0, $t1, end_input

li $v0, 5
 syscall

#Push-Metemos elemento introducido por usuario en Stack/Pila
 addi $sp, $sp, -4
 sw $v0, ($sp)

#step
 addi $t0, $t0, 1

#loop
 j loop_input

end_input:
 move $ra, $t9
 jr $ra

exit:
 li $v0, 10
 syscall
