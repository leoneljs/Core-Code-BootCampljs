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
