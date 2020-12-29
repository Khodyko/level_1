# level_1

import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.math.BigInteger;
import java.util.*;


public class Main {

    public static void main(String[] args) throws Exception {
        //Добрый день дорогой ментор!)
  /*     Basics of software code development
     1. Найдите значение функции: z = ( (a – 3 ) * b / 2) + c.
      a,b,c считаем с клавиатуры, что там за данные неизвестно и по идее можно было бы конечно проверить
        что там вводится и исходя из этого сделать код. Но это не того уровня задачи.
        А я слишком ленив, для того чтобы просто так писать лишний код.
        Лень, говорят, признак хорошего программиста (это конечно шутка).

*/
        BufferedReader bu = new BufferedReader(new InputStreamReader(System.in)); //открываем буфер и инпутстрим
        System.out.println("Задание 1.1");
        System.out.println("Введите  a");
        int a = Integer.parseInt(bu.readLine());
        System.out.println("Введите  b");
        int b = Integer.parseInt(bu.readLine());
        System.out.println("Введите  c");
        int c = Integer.parseInt(bu.readLine());     // инициализируем переменные, через парс, потому что редлайн выдает строку
        int z = ((a - 3) * b / 2) + c;
        System.out.println("z= " + z);

        // будем надеятся, что число будет не дробным или мы потеряем точность)


        // 2. Вычислить значение выражения по формуле (все переменные принимают действительные значения):
        System.out.println("Задание 1.2");
        System.out.println("Введите  a");
        int a_2 = Integer.parseInt(bu.readLine());
        System.out.println("Введите  b");
        int b_2 = Integer.parseInt(bu.readLine());
        System.out.println("Введите  c");
        int c_2 = Integer.parseInt(bu.readLine());
        Double val2; //тут скорее всего конечно будет дробь, так что даубл
        val2 = b_2 + Math.sqrt((b_2 ^ 2) + 4 * a_2 * c_2);
        val2 = val2 / (2 * a_2);
        val2 = val2 - (a_2 ^ 3) * c_2;
        val2 = val2 + Math.sqrt(b_2);     // сделал читабельнее немного

        System.out.println("val1= " + val2);

//  3. Вычислить значение выражения по формуле (все переменные принимают действительные значения)
        System.out.println("Задание 1.3");
        System.out.println("Введите  x");
        Integer x = Integer.parseInt(bu.readLine());
        System.out.println("Введите  y");
        Integer y = Integer.parseInt(bu.readLine());
        Double val3;
        val3 = Math.sin(x) + Math.cos(y);
        val3 = val3 / (Math.cos(x) - Math.sin(y));
        val3 = val3 * Math.tan(x * y);
        System.out.println(val3);
//  4. Дано действительное число R вида nnn.ddd (три цифровых разряда в дробной и целой частях). Поменять местами
//дробную и целую части числа и вывести полученное значение числа.
        System.out.println("Задание 1.4");
        System.out.println("Введите дробное число вида nnn.ddd");
        String r = bu.readLine();    // если это для вывода в консоль, то такое решение через стринг, думаю, удачно
        String rfinal = r.substring(4, 7) + "." + r.substring(0, 3);
        System.out.println(rfinal);
//5. Дано натуральное число Т, которое представляет длительность прошедшего времени в секундах. Вывести
//данное значение длительности в часах, минутах и секундах в следующей форме:
//ННч ММмин SSc
        System.out.println("Задание 1.5");
        System.out.println("Введите количество секунд");
        Integer t = Integer.parseInt(bu.readLine());
        Integer thour = t / 3600; // так как это интеджер, он округлит, мы получим количество часов
        Integer tmin = (t - thour * 3600) / 60; // отнимаем кол-во целых часов в секундах, и оставляем целые минуты
        Integer tsec = t - thour * 3600 - tmin * 60; // остаток от целых часов и минут, это секунды
        System.out.println(thour + " hour");
        System.out.println(tmin + " minute");
        System.out.println(tsec + " second");


//6. Для данной области составить линейную программу, которая печатает true, если точка с координатами (х, у)
//принадлежит закрашенной области, и false — в противном случае
        System.out.println("Задание 1.6");
        Boolean val6 = false;
        System.out.println("Введите x");
        Integer x6 = Integer.parseInt(bu.readLine());
        System.out.println("Введите y");
        Integer y6 = Integer.parseInt(bu.readLine());
        if (y6 <= 4 && y6 >= 0 && x6 <= 2 && x6 >= -2) {
            val6 = true;                                  // проверяем выше оси Х
        } else if (y6 <= 0 && y6 >= -4 && x6 < 4 && x6 > -4) {
            val6 = true;                                  // проверяем ниже оси Х
        }
        if (y6 == -1 && x6 == 0) {
            val6 = false;                                 // проверяем позицию (0,-1)
        }
        System.out.println(val6);
// Ветвления
// 1. Даны два угла треугольника (в градусах). Определить, существует ли такой треугольник, и если да, то будет ли
//он прямоугольным.
        System.out.println("Задание 2.1");
        Boolean val_21 = false;
        System.out.println("Веведите перый угол треугольника");
        Integer angle1 = Integer.parseInt(bu.readLine());
        System.out.println("Веведите второй угол треугольника");
        Integer angle2 = Integer.parseInt(bu.readLine());   // Сумма углов треугольника =180, таким образом
        if (angle2 + angle1 < 180) {                      // сумма двух углов треугольника не может быть >=180
            val_21 = true;                             // true, если такой треугольник существует
        }
        if (angle1 == 90 || angle2 == 90 || angle1 + angle2 == 90) {
            System.out.println("треугольник прямоугольный");
        } else {
            System.out.println("треугольник не прямоугольный");
        }
// 2. Найти max{min(a, b), min(c, d)}
        System.out.println("Задание 2.2");
        System.out.println("Введите четыре переменные");
        Integer a22 = Integer.parseInt(bu.readLine());
        Integer b22 = Integer.parseInt(bu.readLine());
        Integer c22 = Integer.parseInt(bu.readLine());
        Integer d22 = Integer.parseInt(bu.readLine());
        Integer val22 = Math.max(Math.min(a22, b22), Math.min(c22, d22));
        System.out.println(val22);


// 3. Даны три точки А(х1,у1), В(х2,у2) и С(х3,у3). Определить, будут ли они расположены на одной прямой.
        System.out.println("Задание 2.3");
        System.out.println("Введите х1");
        Integer x1_23 = Integer.parseInt(bu.readLine());
        System.out.println("Введите y1");
        Integer y1_23 = Integer.parseInt(bu.readLine());
        System.out.println("Введите х2");
        Integer x2_23 = Integer.parseInt(bu.readLine());
        System.out.println("Введите y2");
        Integer y2_23 = Integer.parseInt(bu.readLine());
        System.out.println("Введите х3");
        Integer x3_23 = Integer.parseInt(bu.readLine());
        System.out.println("Введите y3");
        Integer y3_23 = Integer.parseInt(bu.readLine());


        if (((x3_23 - x1_23) / (x2_23 - x1_23) == (y3_23 - y1_23) / (y2_23 - y1_23))) {            // это уравнение загуглено, но я ему доверяю
            System.out.println(true);
        } else {
            System.out.println(false);
        }


//4. Заданы размеры А, В прямоугольного отверстия и размеры х, у, z кирпича. Определить, пройдет ли кирпич через
//отверстие.
        System.out.println("Задание 2.4");
        Boolean val_24 = false;
        System.out.println("Введите размер отверстия А");
        Integer A_24 = Integer.parseInt(bu.readLine());
        System.out.println("Введите размер отверстия В");
        Integer B_24 = Integer.parseInt(bu.readLine());
        System.out.println("Введите размер кирпича х");
        Integer x_24 = Integer.parseInt(bu.readLine());
        System.out.println("Введите размер кирпича у");
        Integer y_24 = Integer.parseInt(bu.readLine());
        System.out.println("Введите размер кирпича z");
        Integer z_24 = Integer.parseInt(bu.readLine());   //  сравниваю меньшие стороны отверстия и кирпича
        Integer minhole_24 = Math.min(A_24, B_24);
        Integer maxhole_24 = Math.max(A_24, B_24);
        ArrayList<Integer> arr_24 = new ArrayList<>();           //создал эррэй лист добавил в него стороны кирпича
        arr_24.add(x_24);
        arr_24.add(y_24);
        arr_24.add(z_24);
        Collections.sort(arr_24);                                  // отсортировал


        if (arr_24.get(0) <= minhole_24 && arr_24.get(1) <= maxhole_24) { // меньшие стороны кирпича сравнил с меньшими сторонами отверстия
            val_24 = true;
            System.out.println("Кирпич вошел параллельно сторонам");
        }
        else{
            System.out.println("Кирпич не вошел параллельно сторонам");
        }
        Double minbrick = Double.valueOf(arr_24.get(0));
        Double maxbrick = Double.valueOf(arr_24.get(1));
        Double koordX1=0.0;
        Double koordX2=0.0;
        Double halfDiagonalBrick=0.0;
        Double alpha=0.0;
        if(!val_24) {                                                                 // если не вошел параллельно сторонам
            if(minbrick<minhole_24){                                                   // по диагонали пройдет, только если меньшая сторона кирпича
                                                                                        // меньше меньшей стороны отверстия

                halfDiagonalBrick = (Math.sqrt((Math.pow(minbrick , 2)) + (Math.pow(maxbrick,2)))) / 2;
                 koordX1 = maxhole_24 / 2 - Math.sqrt(Math.pow(halfDiagonalBrick, 2)- Math.pow((minhole_24 / 2), 2));
               alpha= Math.PI-(Math.asin((minhole_24/2)/halfDiagonalBrick)+(Math.atan(maxbrick/minbrick)));
                if(koordX1<=0){                                                                                 // кирпича толщиной 0 не бывает
                    val_24=false;                                                                                  // при koordX1=0   диагонали совпали, но стороны не параллельны
                }
                else {
                    koordX2=koordX1-minbrick*Math.cos(alpha);
                    if(koordX2>=0){
                        val_24=true;
                        System.out.println("Кирпич вошел по диагонали");

                    }
                }
            }}

        

        System.out.println(val_24);                                             // решение достаточно сложное математически
                                                                                // в двух словах, исходим из того, что кирпич проходящий по диагонали отверстия
        //совпадает центром своей диагонали с центром диагонали отверстия. Их диагонали не всегда совпадают. Лучшее положение - это касание диагональных углов кирпича
        // бОльших сторон отверстия. Располагаем нижний левый угол отверстия в нуле координат. Находим угол наклона кирпича и координату второго угла, если он не вышел за
        // за ось координат Y - значит кирпич прошел.

// 5. Вычислить значение функции:
        System.out.println("Задание 2.5");
        Integer x_25 = Integer.parseInt(bu.readLine());
        Double val_25;
        if (x_25 <= 3) {
            val_25 = (x_25 ^ 2 - 3 * x_25 + 9) / 1.0;         // Сделал вид что у меня есть Double :B
        } else val_25 = (1 / (x_25 ^ 3 + 6)) / 1.0;

        System.out.println(val_25);

//         Циклы
//1. Напишите программу, где пользователь вводит любое целое положительное число. А программа суммирует
//все числа от 1 до введенного пользователем числа.
        System.out.println("Задание 3.1");
        System.out.println("Введите любое положительное целое число");
        Integer a_31 = Integer.parseInt(bu.readLine()); //  я использую обычгный диапазон, но если Вы хотели сто тысяч миллионов, только попросите)))
        Integer sum_31 = 0;
        for (int i = 0; i <= a_31; i++) {
            sum_31 = sum_31 + i;

        }
        System.out.println(sum_31);


// 2. Вычислить значения функции на отрезке [а,b] c шагом h:
        System.out.println("Задание 3.2");
        System.out.println("Введите любое целое число");
        Integer a_32 = Integer.parseInt(bu.readLine());
        System.out.println("Введите любое целое число больше прошлого");
        Integer b_32 = Integer.parseInt(bu.readLine());
        Integer h_32 = Integer.parseInt(bu.readLine());
        Integer y_32;
        Integer x_32;
        for (int i = a_32; i < b_32; i = i + h_32) {
            x_32 = i;
            if (x_32 > 2) {
                y_32 = x_32;
            } else {
                y_32 = -x_32;
            }
            System.out.println(y_32);
        }

//3. Найти сумму квадратов первых ста чисел.
        System.out.println("Задание 3.3");
        Integer val_33 = 0;
        for (int i = 0; i <= 100; i++) {
            val_33 = val_33 + i;                        // не знаю считаете ли Вы "0" за первое число. Думаю это не важно
        }
        System.out.println(val_33);

// 4. Составить программу нахождения произведения квадратов первых двухсот чисел.
        System.out.println("Задание 3.4");
        BigInteger val_34 = new BigInteger("1");
        BigInteger sum_34 = new BigInteger("1");    // это большое число

        for (int i = 1; i <= 200; i++) {
            val_34 = BigInteger.valueOf(i);

            sum_34 = sum_34.multiply(val_34);
        }
        System.out.println(sum_34);
//5. Даны числовой ряд и некоторое число е. Найти сумму тех членов ряда, модуль которых больше или равен
//заданному е. Общий член ряда имеет вид.
        System.out.println("Задание 3.5");
        ArrayList<Double> arrdbl_35 = new ArrayList<>();
        System.out.println("Введите числа, затем введите Enter");
        Double sum_35 = 0.0;
        Double fukc_35 = 0.0;
        Double val_35;
        while (true) {                                                        // защита от ввода нецифры
            try {
                val_35 = Double.valueOf(bu.readLine());
                break;
            } catch (Exception e) {
                System.out.println("Требуется вести число!");

            }
        }
        while (true) {                                                          //вводим числовой ряд
            arrdbl_35.add(val_35);
            try {
                val_35 = Double.valueOf(bu.readLine());
            } catch (Exception e) {
                break;
            }
        }
        System.out.println("Введите параметр е");
        Double e_35 = Double.valueOf(bu.readLine());
        for (int i = 0; i < arrdbl_35.size(); i++) {
            fukc_35 = (Math.pow(2, -arrdbl_35.get(i))) + (Math.pow(3, -arrdbl_35.get(i)));
            if ((fukc_35) >= e_35) {
                sum_35 = sum_35 + fukc_35;
            }


        }
        System.out.println("Сумма  = " + sum_35);


//6. Вывести на экран соответствий между символами и их численными обозначениями в памяти компьютера.
        System.out.println("Задание 3.6");
        char a_36;
        for (int i = -128; i < 127; i++) {
            a_36 = (char) i;
            System.out.println(i + " = " + a_36);}

// 7. Для каждого натурального числа в промежутке от m до n вывести все делители, кроме единицы и самого числа.
//m и n вводятся с клавиатуры.
            System.out.println("Задание 3.7");
            System.out.println("Введите m");
            Integer m_37 = Integer.parseInt(bu.readLine());
            System.out.println("Введите n, которое больше n");
            Integer n_37 = Integer.parseInt(bu.readLine());

            for (int i = m_37; i < n_37; i++) {
                System.out.print("делители для " + i + ": ");
                for (int j = 1; j <= n_37; j++) {

                    if (j != 1 && j != i && i % j == 0) {     // если у числа нет остатка от деления значит он делится нацело
                        System.out.print(j + " ");
                    }
                }
                System.out.println();
            }


//8. Даны два числа. Определить цифры, входящие в запись как первого так и второго числа.
            System.out.println("Задание 3.8");
            System.out.println("Введите первое число");
            String a_38 = bu.readLine();                      // я немного хитрю, что принимаю сразу строку, но пользователь не заметит)
            System.out.println("Введите второе число");
            String b_38 = bu.readLine();
            Set<Character> charset_38 = new HashSet<>();      //set не может содержать повторы, пользуемся этим
            for (int i = 0; i < a_38.length(); i++) {
                for (int j = 0; j < b_38.length(); j++) {   // сравниваем каждый символ строки

                    if ((b_38.charAt(j)) == (a_38.charAt(i))) {
                        charset_38.add(a_38.charAt(i));         // добавляем в сет, если есть совпадение
                    }
                }

            }
            for (Character charprint_38 : charset_38) {
                System.out.print(charprint_38);

            }


        }


    }
