# C++ Primer Plus 6th习题

## 第二章

1. 编写一个C++程序，它显示您的姓名和地址。

   ```c++
   #include <iostream>
   using namespace std;
   int main(void)
   {
   	char name[] = "weizixu";
   	char address[4] = {'H', 'I', 'T', '\0'};
   	cout << "我的姓名是：" << name << endl;
   	cout << "我的地址是：" << address << endl;
   	system("pause");
   	return 0;
   }
   ```

2. 编写一个C++程序，它要求用户输入一个以long为单位的距离，然后将它转换为码（一long等于220码）。

   ```c++
   #include <iostream>
   using namespace std;
   int main(void)
   {
   	int d;
   	cout << "请输入要转换的距离：" << endl;
   	cin >> d;
   	cout << "转换后的距离是:" << d*220 << "码" << endl;
   	system("pause");
   	return 0;
   }
   ```

3. 编写一个C++程序，它使用3个用户定义的函数（包括main( )），并生成下面的输出：

   ![](https://archive.biliimg.com/bfs/archive/17cf31d57cd0e8d2301e09e1c689dd7d711c12cb.png)

   其中一个函数要调用两次，该函数生成前两行；另一个函数也被调用两次，并生成其余的输出。

   ```c++
   #include <iostream>
   using namespace std;
   void func1()
   {
   	cout << "Three blind mice" << endl;
   }
   void func2()
   {
   	cout << "See how they run" << endl;
   }
   int main(void)
   {
   	func1();
   	func1();
   	func2();
   	func2();
   	system("pause");
   	return 0;
   }
   ```

4. 编写一个程序，让用户输入其年龄，然后显示该年龄包含多少个月

   ```c++
   #include <iostream>
   using namespace std;
   void year2month(int y)
   {
   	cout << "该年龄包含 " << y*12 << " 个月" << endl;
   }
   
   int main(void)
   {
   	int a;
   	cout << "请输入您的年龄：" << endl;
   	cin >> a;
   	year2month(a);
   	system("pause");
   	return 0;
   }
   ```

5. 编写一个程序，其中的main( )调用一个用户定义的函数（以摄氏温度值为参数，并返回相应的华氏温度值）。该程序按下面的格式要求用户输入摄氏温度值，并显示结果：

   ![](https://archive.biliimg.com/bfs/archive/9b6137d3f82d0a4459eb83152f5e8d7813f6b056.png)

   下面是转换公式：

   华氏温度 = 1.8×摄氏温度 + 32.0

   ```c++
   #include <iostream>
   using namespace std;
   void cel2fah(float c)
   {
   	cout << c << "degrees Celsius is " << c * 1.8 + 32.0 << " degrees Fahrenheit." << endl;
   }
   
   int main(void)
   {
   	float t;
   	cout << "Please enter a Celsius value：" << endl;
   	cin >> t;
   	cel2fah(t);
   	system("pause");
   	return 0;
   }
   ```

6. 编写一个程序，其main( )调用一个用户定义的函数（以光年值为参数，并返回对应天文单位的值）。该程序按下面的格式要求用户输入光年值，并显示结果：

   ![](https://archive.biliimg.com/bfs/archive/7cb33f2f7bb385c9acc789095cded8ce12ea45c1.png)

   ```c++
   #include <iostream>
   #include<stdio.h>
   using namespace std;
   void ly2au(double c)
   {
   	cout << c << "light years = " << c * 63240 << " astronomical units." << endl;
   }
   
   int main(void)
   {
   	double light;
   	printf("Enter the number of light years：");
   	cin >> light;
   	ly2au(light);
   	system("pause");
   	return 0;
   }
   ```

7. 编写一个程序，要求用户输入小时数和分钟数。在main( )函数中，将这两个值传递给一个void函数，后者以下面这样的格式显示这两个值：

   ![](https://archive.biliimg.com/bfs/archive/22e66b948302d84700fd7c9b92f83fa02518f9e9.png)

   ```c++
   #include <iostream>
   #include<stdio.h>
   using namespace std;
   void showtime(int h, int m)
   {
   	cout << "Time: " << h << " : " << m << endl;
   }
   
   int main(void)
   {
   	int h, m;
   	printf("Enter the number of hours：");
   	cin >> h;
   	printf("Enter the number of minutes：");
   	cin >> m;
   	showtime(h, m);
   	system("pause");
   	return 0;
   }
   ```

## 第三章

1. 编写一个小程序，要求用户使用一个整数指出自己的身高（单位为英寸），然后将身高转换为英尺和英寸。该程序使用下划线字符来指示输入位置。另外，使用一个const符号常量来表示转换因子。

   ```c++
   #include<iostream>
   using namespace std;
   const double factor=0.0833333;
   int main()
   {
   	double height;
   	cin >> height ;
   	cout << height*factor << endl;
   	system("pause");
   	return 0;
   }
   ```

2. 编写一个小程序，要求以几英尺几英寸的方式输入其身高，并以磅为单位输入其体重。（使用3个变量来存储这些信息。）该程序报告其BMI（Body Mass Index，体重指数）。为了计算BMI，该程序以英寸的方式指出用户的身高（1英尺为12英寸），并将以英寸为单位的身高转换为以米为单位的身高（1英寸=0.0254米）。然后，将以磅为单位的体重转换为以千克为单位的体重（1千克=2.2磅）。最后，计算相应的BMI—体重（千克）除以身高（米）的平方。用符号常量表示各种转换因子。
   $$
   a英尺,b英寸,c磅\\
   BMI=\frac{\frac{c}{2.2}}{(0.0254*(12a+b))^2}
   $$
   

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<cmath>
   using namespace std;
   const double factor1 = 2.2, factor2 = 0.0254, factor3 = 12;
   int main(void)
   {
   	double a, b, c, bmi;
   	printf("Enter your height and weight：");
   	cin >> a >> b >> c;
   	bmi = (c / factor1) / pow((factor2 * (factor3 * a + b)), 2);
   	printf("BMI Index is ：%f", bmi);
   	system("pause");
   	return 0;
   }
   ```

3. 编写一个程序，要求用户以度、分、秒的方式输入一个纬度，然后以度为单位显示该纬度。1度为60分，1分等于60秒，请以符号常量的方式表示这些值。对于每个输入值，应使用一个独立的变量存储它。下面是该程序运行时的情况：

   ![](https://archive.biliimg.com/bfs/archive/e3345201ebfa9a30f10b492e00d23f44e658a6da.png)

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<cmath>
   using namespace std;
   const double factor = 60;
   int main(void)
   {
   	double d, m, s, result;
   	printf("Enter a latitude in degrees, minutes and seconds：");
   	cin >> d >> m >> s;
   	result = d + m/factor + s/pow(factor, 2);
   	printf("%f degrees, %f minutes, %f seconds = %f degrees", d, m, s, result);
   	system("pause");
   	return 0;
   }
   ```

4. 编写一个程序，要求用户以整数方式输入秒数（使用long或long long变量存储），然后以天、小时、分钟和秒的方式显示这段时间。使用符号常量来表示每天有多少小时、每小时有多少分钟以及每分钟有多少秒。该程序的输出应与下面类似：

   ![](https://archive.biliimg.com/bfs/archive/dc6faebd6bdcfbff676186c5b94df58a7fb8c086.png)
   $$
   1\quad day=86400\quad seconds\\
   1\quad hour = 3600\quad seconds\\
   1\quad minute = 60\quad seconds\\
   $$

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<cmath>
   using namespace std;
   int main(void)
   {
   	long s;
   	double d, h, m, se;
   	printf("Enter the number of seconds：");
   	cin >> s;
   	d = s / 86400, h = s % 86400 / 3600, m = s % 86400 % 3600 / 60, se = s % 86400 % 3600 % 60;
   	printf("%d seconds = %f days, %f hours, %f minutes, %f seconds", s, d, h, m, se);
   	system("pause");
   	return 0;
   }
   ```

   **注意：**long类型本质还是 **int** 型，所以输出还是要用 **%d**

5. 编写一个程序，要求用户输入全球当前的人口和美国当前的人口（或其他国家的人口）。将这些信息存储在long long变量中，并让程序显示美国（或其他国家）的人口占全球人口的百分比。该程序的输出应与下面类似：

   ![](https://archive.biliimg.com/bfs/archive/4b708060c4d3a8f20758750109b1fee8ddb1aca6.png)

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<cmath>
   using namespace std;
   int main(void)
   {
   	long long glp, usp;
   	float per;
   	printf("Enter the world's population：");
   	cin >> glp;
   	printf("Enter the population of the US：");
   	cin >> usp;
   	per = float(100*usp / glp);
   	// cout << per << endl;
   	printf("The population of the US is %.2f %% of the world population", per);
   	system("pause");
   	return 0;
   }
   ```

6. 编写一个程序，要求用户输入驱车里程（英里）和使用汽油量（加仑），然后指出汽车耗油量为一加仑的里程。如果愿意，也可以让程序要求用户以公里为单位输入距离，并以升为单位输入汽油量，然后指出欧洲风格的结果—即每100公里的耗油量（升）。

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<cmath>
   using namespace std;
   int main(void)
   {
   	float mile, gal, per;;
   	printf("Enter mile：");
   	cin >> mile;
   	printf("Enter gal：");
   	cin >> gal;
   	per = mile / gal;
   	printf("miles per gal is %.2f miles", per);
   	system("pause");
   	return 0;
   }
   ```

7. 编写一个程序，要求用户按欧洲风格输入汽车的耗油量（每100公里消耗的汽油量（升）），然后将其转换为美国风格的耗油量—每加仑多少英里。注意，除了使用不同的单位计量外，美国方法（距离/燃料）与欧洲方法（燃料/距离）相反。100公里等于62.14英里，1加仑等于3.875升。因此，19mpg大约合12.4l/100km，l27mpg大约合8.71/100km。
   $$
   输入欧洲风格耗油量为:e=62.14英里/升=62.14*3.875英里/加仑
   $$

## 第四章

1. 编写一个C++程序，如下述输出示例所示的那样请求并显示信息：

   ![](https://archive.biliimg.com/bfs/archive/2a14ee5edcfd31940c448dd2b0484d48b4fdd31b.png)

   注意，该程序应该接受的名字包含多个单词。另外，程序将向下调整成绩，即向上调一个字母。假设用户请求A、B或C，所以不必担心D和F之间的空档。

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   using namespace std;
   int main(void)
   {
   	string firstname, lastname;
   	char grade;
   	int age;
   	cout << "what is your first name? " << endl;
   	getline(cin, firstname);
   	cout << "what is your last name? " << endl;
   	getline(cin, lastname);
   	cout << "what letter grade do you deserve? " << endl;
   	cin >> grade;
   	printf("what is your first age? ");
   	cin >> age;
   	printf("Name: %s , %s\n", lastname.c_str(), firstname.c_str());
   	cout << "Grade: " << (char)(grade + 1) << endl;
   	cout << "Age: " << age << endl;
   	system("pause");
   	return 0;
   }
   ```

2. 修改程序清单4.4，使用C++ string类而不是char数组

   ```c++
   #include <iostream>
   #include<string>
   using namespace std;
   int main(void)
   {
   	string name, dessert;
   	cout << "enter your name:\n ";
   	getline(cin, name);
   	cout << "enter your favourite dessert:\n" << endl;
   	getline(cin, dessert);
   	cout << "I have some delicious " << dessert;
   	cout << " for you,  " << name << endl;
   	system("pause");
   	return 0;
   }
   ```

3. 编写一个程序，它要求用户首先输入其名，然后输入其姓；然后程序使用一个逗号和空格将姓和名组合起来，并存储和显示组合结果。请使用char数组和头文件cstring中的函数。下面是该程序运行时的情形：

   ![](https://archive.biliimg.com/bfs/archive/31c805dfbfbe3d62af8c0224a4976c48c0be0417.png)

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<cstring>
   #include<string>
   using namespace std;
   int main(void)
   {
   	char firstname[20], lastname[20];
   	char temp[] = " , ";
   	cout << "enter your first name? " << endl;
   	cin.getline(firstname, 20);
   	cout << "enter your last name? " << endl;
   	cin.getline(lastname, 20);
   	int len1 = strlen(firstname) + strlen(temp) + 1;
   	int len2 = strlen(firstname) + strlen(temp) + strlen(lastname) + 1;
   	strcat_s(firstname, len1, temp);
   	strcat_s(firstname, len2, lastname);
   	cout << firstname << endl;
   	cout << "Here is the information in a single string: " << firstname << endl;
   	
   	system("pause");
   	return 0;
   }
   
   //注意：Visual Studio中不支持strcat函数，需要用strcat_s(str1, len, str2)函数代替
   //str1和str2是要连接的两个字符串，len是连接后的字符串长度
   ```

4. 编写一个程序，它要求用户首先输入其名，再输入其姓；然后程序使用一个逗号和空格将姓和名组合起来，并存储和显示组合结果。请使用string对象和头文件string中的函数。下面是该程序运行时的情形：

   ![](https://archive.biliimg.com/bfs/archive/31c805dfbfbe3d62af8c0224a4976c48c0be0417.png)

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   using namespace std;
   int main(void)
   {
   	string firstname, lastname, str;
   	string temp = " , ";
   	cout << "enter your first name? " << endl;
   	getline(cin, firstname);
   	cout << "enter your last name? " << endl;
   	getline(cin, lastname);
   	str = firstname + temp + lastname;
   	cout << str << endl;
   	cout << "Here is the information in a single string: " << str << endl;
   	
   	system("pause");
   	return 0;
   }
   ```

5. 结构CandyBar包含3个成员。第一个成员存储了糖块的品牌；第二个成员存储糖块的重量（可以有小数）；第三个成员存储了糖块的卡路里含量（整数）。请编写一个程序，声明这个结构，创建一个名为snack的CandyBar变量，并将其成员分别初始化为“Mocha Munch”、2.3和350。初始化应在声明snack时进行。最后，程序显示snack变量的内容。

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   using namespace std;
   struct CandyBar
   {
   	string brand;
   	float weight;
   	int cal;
   }snack =
   {
   	"Mocha Munch",
   	2.3,
   	350
   };
   int main(void)
   {
   	/*strcpy(snack.brand, "Mocha Munch");
   	snack.weight = 2.3;
   	snack.cal = 350;*/
   	cout << "The snack's name: " << snack.brand << endl;
   	cout << "The snack's Weight: " << snack.weight << endl;
   	cout << "The snack's Vol: " << snack.cal << endl;
   	system("pause");
   	return 0;
   }
   ```

6. 结构CandyBar包含3个成员，如编程练习5所示。请编写一个程序，创建一个包含3个元素的CandyBar数组，并将它们初始化为所选择的值，然后显示每个结构的内容。

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   using namespace std;
   struct CandyBar
   {
   	string brand;
   	float weight;
   	int cal;
   }snack;
   
   int main(void)
   {
   	CandyBar Member[3] =
   	{
   		{"xiangjingjianyu", 1, 100},
   		{"youbing", 2, 200},
   		{"lizhi", 3, 300}
   	};
   	int i;
   	for (i = 0; i < 3; i++)
   	{
   		cout << "Member " << i << " 's name: " << Member[i].brand << endl;
   		cout << "Member " << i << " 's weight: " << Member[i].weight << endl;
   		cout << "Member " << i << " 's cal: " << Member[i].cal << endl;
   	}
   	
   	system("pause");
   	return 0;
   }
   ```

7. William Wingate从事比萨饼分析服务。对于每个披萨饼，他都需要记录下列信息：

   - 披萨饼公司的名称，可以有多个单词组成。
   - 披萨饼的直径。
   - 披萨饼的重量。

   请设计一个能够存储这些信息的结构，并编写一个使用这种结构变量的程序。程序将请求用户输入上述信息，然后显示这些信息。请使用cin（或它的方法）和cout。

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   using namespace std;
   struct Pizza
   {
   	string company;
   	float diameter;
   	int weight;
   }pizza;
   
   int main(void)
   {
   	string name;
   	float d, w;
   	cout << "enter the company's name: " << endl;
   	getline(cin, name);
   	cout << "enter pizza's diameter and weight: " << endl;
   	cin >> d >> w;
   	pizza.company = name;
   	pizza.weight = w;
   	pizza.diameter = d;
   
   	cout << "company's name: " << pizza.company << endl;
   	cout << "pizza's diameter: " << pizza.diameter << endl;
   	cout << "pizza's weight: " << pizza.weight << endl;
   	
   	system("pause");
   	return 0;
   }
   ```

8. 完成编程练习7，但使用new来为结构分配内存（即：用指针），而不是声明一个结构变量。另外，让程序在请求输入比萨饼公司名称之前输入比萨饼的直径。

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   using namespace std;
   struct Pizza
   {
   	string company;
   	float diameter;
   	int weight;
   };
   
   int main(void)
   {
   	Pizza *ps = new Pizza;
   	cout << "enter pizza's diameter: " << endl;
   	cin >> ps ->diameter;
   	cin.get();
   	cout << "enter the company's name: " << endl;
   	getline(cin, ps ->company);
   	cout << "enter pizza's weight: " << endl;
   	cin >> ps->weight;
   	cout << "company's name: " << ps ->company << endl;
   	cout << "pizza's diameter: " << ps ->diameter << endl;
   	cout << "pizza's weight: " << ps ->weight << endl;
   	delete ps;
   	system("pause");
   	return 0;
   }
   ```

9. 完成编程练习6，但使用new来动态分配数组，而不是声明一个包含3个元素的CandyBar数组。

   ```c++
   #include<iostream>
   #include<cstring>
   #include<string>
   struct CandyBar
   {
   	std::string band;
   	double Weight;
   	int Vol;
   };
   int main()
   {
   	using namespace std;
   	CandyBar *ps = new CandyBar [3];
   	int i;
   	
   	for(i=0;i<3;i++)
   	{
   		ps[i].band = "haharayu";
   		ps[i].Vol = 233;
   		ps[i].Weight = 2.33;
   	}
   	
   	for(i=0;i<3;i++)
   	{
   		cout <<ps[i].band << ", ";
   		cout << ps[i].Vol << ", ";
   		cout << ps[i].Weight << endl;
   	}
   	delete [] ps;
   	system("pause");
   	return 0;
   }
   ```

10. 编写一个程序，让用户输入三次40码跑的成绩（如果您愿意，也可让用户输入40米跑的成绩），并显示次数和平均成绩。请使用一个array对象来存储数据（如果编译器不支持array类，请使用数组）。

    ```c++
    #include <iostream>
    #include<stdio.h>
    #include<string>
    #include<array>
    using namespace std;
    int main(void)
    {
    	array <float, 3> score{0, 0, 0};
    	cout << "enter your scores: " << endl;
    	int i, sum=0;
    	for (i = 0; i < 3; i++)
    	{
    		cout << "请输入第 " << i + 1 << " 次成绩：" << endl;
    		cin >> score.at(i);
    		cout << "第 " << i+1 << " 次的成绩为：" << score.at(i) << endl;
    		sum += score.at(i);
    	}
    	float ave;
    	ave = sum / 3;
    	cout << "The average score is：" << ave << endl;
    	system("pause");
    	return 0;
    }
    ```

## 第五章

1. 编写一个要求用户输入两个整数的程序。该程序将计算并输出这两个整数之间（包括这两个整数）所有整数的和。这里假设先输入较小的整数。例如，如果用户输入的是2和9，则程序将指出2～9之间所有整数的和为44。

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   #include<array>
   using namespace std;
   int main(void)
   {
   	int a, b, i, sum = 0;
   	cin >> a >> b;
   	for (i = a; i < b + 1; i++)
   	{
   		sum += i;
   	}
   	cout << "The summary between " << a <<  " and " << b << " is：" << sum << endl;
   	system("pause");
   	return 0;
   }
   ```

2. 使用array对象（而不是数组）和long double（而不是long long）重新编写程序清单5.4，并计算100!的值。

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   #include<array>
   using namespace std;
   int main(void)
   {
   	int i, k;
   	cout << "请输入要计算阶乘的数字：" << endl;
   	cin >> i;
   	array <long double, 101> arr{1, 1};
   
   	for (k = 2; k < i+1; k++)
   	{
   		arr.at(k) = k * arr.at(k - 1);
   	}
   	for (k = 0; k < i+1; k++)
   	{
   		cout.setf(ios::fixed, ios::floatfield);//十进制计数法，不是科学计数法
   		cout << k << "! = " << arr.at(k) << endl;
   	}
   	system("pause");
   	return 0;
   }
   ```

3. 编写一个要求用户输入数字的程序。每次输入后，程序都将报告到目前为止，所有输入的累计和。当用户输入0时，程序结束。

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   #include<array>
   using namespace std;
   int main(void)
   {
   	int a, sum=0;
   	cout << "请输入数字：" << endl;
   	cin >> a;
   	sum += a;
   	while (a != 0)
   	{
   		cout << "请输入数字：" << endl;
   		cin >> a;
   		sum += a;
   	}
   	cout << "数字之和为：" << sum << endl;
   	system("pause");
   	return 0;
   }
   ```

4. Daphne以10%的单利投资了100美元。也就是说，每一年的利润都是投资额的10%，即每年10美元：
   $$
   利息 = 0.10×原始存款
   $$
   而Cleo以5%的复利投资了100美元。也就是说，利息是当前存款（包括获得的利息）的5%，：
   $$
   利息 = 0.05×当前存款
   $$
   Cleo在第一年投资100美元的盈利是5%—得到了105美元。下一年的盈利是105美元的5%—即5.25美元，依此类推。请编写一个程序，计算多少年后，Cleo的投资价值才能超过Daphne的投资价值，并显示此时两个人的投资价值。

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   #include<array>
   #include<cmath>
   using namespace std;
   int main(void)
   {
   	double d = 100, c = 100;
   	int i;
   	for (i = 1; ; i++)
   	{
   		d += 10 * i;
   		c *= pow(1.05, (double)i);
   		if (c > d)
   		{
   			cout << "第 " << i << " 年时，Cleo的投资价值超过Daphne的投资价值" << endl;
   			cout << "Daphne的投资价值为： " << d << " 美元" << endl;
   			cout << "Cleo的投资价值为： " << c << " 美元" << endl;
   			break;
   		}
   	}
   	
   	system("pause");
   	return 0;
   }
   ```

5. 假设要销售《C++ For Fools》一书。请编写一个程序，输入全年中每个月的销售量（图书数量，而不是销售额）。程序通过循环，使用初始化为月份字符串的char *数组（或string对象数组）逐月进行提示，并将输入的数据储存在一个int数组中。然后，程序计算数组中各元素的总数，并报告这一年的销售情况。

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   #include<array>
   #include<cmath>
   using namespace std;
   int main(void)
   {
   	const char *month[12] = { "一月", "二月", "三月", "四月", "五月", "六月", "七月", "八月", "九月", "十月", "十一月", "十二月" };  //必须是const char *month，否则会报错
   	//string month[12] = { "一月", "二月", "三月", "四月", "五月", "六月", "七月", "八月", "九月", "十月", "十一月", "十二月" };
   	int salenum[12];
   	int sum = 0;
   	for (int i = 0; i < 12; i++)
   	{
   		cout << month[i] << "的销售量为：";
   		cin >> salenum[i];
   		sum += salenum[i];
   	}
   	cout << "全年销售量为：" << sum << endl;
   	system("pause");
   	return 0;
   }
   ```

6. 完成编程练习5，但这一次使用一个二维数组来存储输入—3年中每个月的销售量。程序将报告每年销售量以及三年的总销售量。

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   #include<array>
   #include<cmath>
   using namespace std;
   int main(void)
   {
   	const char* month[3][12] = { { "一月", "二月", "三月", "四月", "五月", "六月", "七月", "八月", "九月", "十月", "十一月", "十二月" },
   		{ "一月", "二月", "三月", "四月", "五月", "六月", "七月", "八月", "九月", "十月", "十一月", "十二月" },
   		{ "一月", "二月", "三月", "四月", "五月", "六月", "七月", "八月", "九月", "十月", "十一月", "十二月" } };  //必须是const char *month，否则会报错
   	/*string month[3][12] = {{"一月", "二月", "三月", "四月", "五月", "六月", "七月", "八月", "九月", "十月", "十一月", "十二月"},
   	{ "一月", "二月", "三月", "四月", "五月", "六月", "七月", "八月", "九月", "十月", "十一月", "十二月" },
   	{ "一月", "二月", "三月", "四月", "五月", "六月", "七月", "八月", "九月", "十月", "十一月", "十二月" }};*/
   	int salenum[12];
   	int sum = 0;
   	for (int i = 0; i < 3; i++)
   	{
   		for (int j = 0; j < 12; j++)
   		{
   			cout << month[i][j] << "的销售量为：";
   			cin >> salenum[i];
   			sum += salenum[i];
   		}
   		
   	}
   	cout << "三年销售量为：" << sum << endl;
   	system("pause");
   	return 0;
   }
   ```

7. 设计一个名为car的结构，用它存储下述有关汽车的信息：生产商（存储在字符数组或string对象中的字符串）、生产年份（整数）。编写一个程序，向用户询问有多少辆汽车。随后，程序使用new来创建一个由相应数量的car结构组成的动态数组。接下来，程序提示用户输入每辆车的生产商（可能由多个单词组成）和年份信息。请注意，这需要特别小心，因为它将交替读取数值和字符串（参见第4章）。最后，程序将显示每个结构的内容。该程序的运行情况如下：

   ![](https://archive.biliimg.com/bfs/archive/55b435e5b844cd4b9d47df4841a9af3f350c2611.png)

   ```c++
   #include <iostream>
   #include<stdio.h>
   #include<string>
   #include<array>
   #include<cmath>
   using namespace std;
   struct car
   {
   	string manu;
   	int year;
   };
   int main(void)
   {
   	int num;
   	cout << "How many cars do you wish to catalog? ";
   	cin >> num;
   	car* che = new car[num];
   	for (int i = 0; i < num; i++)
   	{
   		cin.get(); //先读取上一行留下来的换行符，然后再读取下一个字符串
   		cout << "Car #" << i + 1 << endl;
   		cout << "Please enter the make: ";
   		getline(cin, che[i].manu);
   		cout << "Please enter the year made: ";
   		cin >> che[i].year;
   	}
   	cout << "Here is your collection:" << endl;
   	for (int i = 0; i < num; i++)
   	{
   		cout << che[i].year << " " << che[i].manu << endl;
   	}
   	system("pause");
   	return 0;
   }
   ```

8. 编写一个程序，它使用一个char数组和循环来每次读取一个单词，直到用户输入done为止。随后，该程序指出用户输入了多少个单词（不包括done在内）。下面是该程序的运行情况：![](https://archive.biliimg.com/bfs/archive/ce0bda87796416640acbde7b884cb4eeecd0267d.png)

   您应在程序中包含头文件cstring，并使用函数strcmp( )来进行比较测试

   ```c++
   #include<iostream>
   #include<string>
   #include<cstring>
   int main()
   {
   	using namespace std;
   	int i;
   	char word[30];
   	cin >> word;
   	//cout << word << endl;
   	for (i = 0; strcmp(word, "done"); i++)  //只要word和done不相同，就一直循环
   	{
   		cin >> word;   //word是一维数组，所以这里并不是在追加字符串
   	}
   	cout << i << endl;
   	system("pause");
   	return 0;
   }
   ```

9. 编写一个满足前一个练习中描述的程序，但使用string对象而不是字符数组。请在程序中包含头文件string，并使用关系运算符来进行比较测试。

   ```c++
   #include<iostream>
   #include<string>
   #include<cstring>
   int main()
   {
   	using namespace std;
   	int i;
   	string word;
   	cin >> word;
   	//cout << word << endl;
   	for (i = 0; word != "done"; i++)  //只要word和done不相同，就一直循环
   	{
   		cin >> word;
   	}
   	cout << i << endl;
   	system("pause");
   	return 0;
   }
   ```

10. 编写一个使用嵌套循环的程序，要求用户输入一个值，指出要显示多少行。然后，程序将显示相应行数的星号，其中第一行包括一个星号，第二行包括两个星号，依此类推。每一行包含的字符数等于用户指定的行数，在星号不够的情况下，在星号前面加上句点。该程序的运行情况如下：

   ![](https://archive.biliimg.com/bfs/archive/2355013b263e51455364b1a23caaddbcbeb57447.png)

   ```c++
   #include<iostream>
   #include<string>
   #include<cstring>
   int main()
   {
   	using namespace std;
   	int num;
   	cout << "Enter the number of rows: ";
   	cin >> num;
   	for(int i = 1; i < num + 1; i++)
   	{
   		for (int j = 0; j < num - i; j++)
   		{
   			cout << ".";
   		}
   		for (int k = 0; k < i; k++)
   		{
   			cout << "*";
   		}
   		cout << endl;
   	}
   	system("pause");
   	return 0;
   }
   ```

   

## 第六章

1. 编写一个程序，读取键盘输入，直到遇到@符号为止，并回显输入（数字除外），同时将大写字符转换为小写，将小写字符转换为大写（别忘了cctype函数系列）

   | 函 数 名 称 |                           返 回 值                           |
   | :---------: | :----------------------------------------------------------: |
   | isalnum( )  |       如果参数是字母数字，即字母或数字，该函数返回true       |
   | isalpha( )  |                如果参数是字母，该函数返回true                |
   | iscntrl( )  |              如果参数是控制字符，该函数返回true              |
   | isdigit( )  |            如果参数是数字（0～9），该函数返回true            |
   | isgraph( )  |        如果参数是除空格之外的打印字符，该函数返回true        |
   | islower( )  |              如果参数是小写字母，该函数返回true              |
   | isprint( )  |        如果参数是打印字符（包括空格），该函数返回true        |
   | ispunct( )  |              如果参数是标点符号，该函数返回true              |
   | isspace( )  | 如果参数是标准空白字符，如空格、进纸、换行符、回车、水平制表符或者垂直制表符，该函数返回true |
   | isupper( )  |              如果参数是大写字母，该函数返回true              |
   | isxdigit( ) |  如果参数是十六进制数字，即0～9、a～f或A～F，该函数返回true  |
   | tolower( )  |       如果参数是大写字符，则返回其小写，否则返回该参数       |
   | toupper( )  |       如果参数是小写字符，则返回其大写，否则返回该参数       |

   ```c++
   #include<iostream>
   #include<cctype>
   using namespace std;
   int main()
   {
   	char ch;
   	cout << "请输入字符：" << endl;
   	cin.get(ch);
   	cin.ignore();
   	while (ch != '@')
   	{
   		if (isalpha(ch))
   		{
   			if (isupper(ch))
   			{
   				cout << "大写转小写：" << (char)tolower(ch) << endl;
   			}
   			else if (islower(ch))
   			{
   				cout << "小写转大写：" << (char)toupper(ch) << endl;
   			}
   		}
   		else if (!isdigit(ch))
   		{
   			cout << "既不是字母也不是数字，直接输出：" << ch << endl;
   		}
   		cin.get(ch);
   		cin.ignore();
   	}
       system("pause");
       return 0;
   }
   ```

2. 编写一个程序，最多将10个donation值读入到一个double数组中（如果您愿意，也可使用模板类array）。程序遇到非数字输入时将结束输入，并报告这些数字的平均值以及数组中有多少个数字大于平均值。

   ```c++
   #include<iostream>
   #include<array>
   using namespace std;
   int main()
   {
   	array <double, 10> arr;
   	arr.fill(0);
   	double sum = 0, ave = 0;
   	int i = 0, count = 0;
   	cout << "请输入第" << i + 1 << "个donation值：" << endl;
   	while (i < 10 && cin >> arr.at(i))
   	{
   		cout << "请输入第" << i+2 << "个donation值：" << endl;
   		sum += arr.at(i);
   		if (i == 9)break;
   		i++;
   	}
   	ave = sum / 10;
   	cout << "总和为：" << sum << endl;
   	cout << "平均值为：" << ave << endl;
   	for (int j = 0; j <= i; j++)
   	{
   		if (arr.at(j) > ave)count++;
   	}
   	cout << "大于平均值的数字有 " << count << " 个" << endl;
   	system("pause");
   	return 0;
   }
   ```

3. 编写一个菜单驱动程序的雏形。该程序显示一个提供4个选项的菜单——每个选项用一个字母标记。如果用户使用有效选项之外的字母进行响应，程序将提示用户输入一个有效的字母，直到用户这样做为止。然后，该程序使用一条switch语句，根据用户的选择执行一个简单操作。该程序的运行情况如下：

   ![](https://archive.biliimg.com/bfs/archive/af23fadb59165c57c8bdf5441e6f430bd65f19fd.png)

   ```c++
   #include<iostream>
   using namespace std;
   int main()
   {
   	char ch;
   	int flag = 1;
   	cout << "Please enter one of the following choices：" << endl;
   	cout << "c)  carnivore          p)  pianist" << endl;
   	cout << "t)  tree               g)  game" << endl;
   	while (flag)
   	{
   		cin.get(ch);
   		cin.ignore();
   		switch (ch)
   		{
   		case 'c':
   			cout << "tiger is carnivore." << endl;
   			flag = 0;
   			break;
   		case 'p':
   			cout << "She is a pianist." << endl;
   			flag = 0;
   			break;
   		case 't':
   			cout << "A maple is a tree." << endl;
   			flag = 0;
   			break;
   		case 'g':
   			cout << "Eenie Meenie is a game." << endl;
   			flag = 0;
   			break;
   		default:
   			cout << "please enter a c, p, t, or g: ";
   		}
   	}
   	system("pause");
   	return 0;
   }
   ```

4. 加入Benevolent Order of Programmer后，在BOP大会上，人们便可以通过加入者的真实姓名、头衔或秘密BOP姓名来了解他（她）。请编写一个程序，可以使用真实姓名、头衔、秘密姓名或成员偏好来列出成员。编写该程序时，请使用下面的结构：

   ![](https://archive.biliimg.com/bfs/archive/06a9c7b9d6375cf2504d500b53c8f117631b4e9d.png)

   该程序创建一个由上述结构组成的小型数组，并将其初始化为适当的值。另外，该程序使用一个循环，让用户在下面的选项中进行选择：

   ![](https://archive.biliimg.com/bfs/archive/e3cd4645d806c90113838d52f8584487c4235ee3.png)

   注意，“display by preference”并不意味着显示成员的偏好，而是意味着根据成员的偏好来列出成员。例如，如果偏好号为1，则选择d将显示程序员的头衔。该程序的运行情况如下：

   ![](https://archive.biliimg.com/bfs/archive/1b74a34253ea1196c62a746a86fec52297151e12.png)

   ```c++
   #include<iostream>
   #include<string>
   using namespace std;
   const int membercount = 5;
   struct bop
   {
   	string fullname;
   	string title;
   	string bopname;
   	int preference;
   };
   int main()
   {
   	int i;
   	bop member[membercount];
   	for (i = 0; i < membercount; i++)
   	{
   		cout << "请输入第 " << i + 1 << " 个成员的信息：" << endl;
   		cin.ignore();
   		getline(cin, member[i].fullname);
   		getline(cin, member[i].title);
   		getline(cin, member[i].bopname);
   		cin >> member[i].preference;
   	}
   	cout << "Benevolent Order of Programmers Report：" << endl;
   	cout << "a. display by name\tb. display by title\n"
   		 << "c. displya by bopname   d. display by prefence\n"
   		 << "q. quit\n";
   	cout << "Enter your choice：" << endl;
   	char ch;
   	while (cin >> ch)
   	{
   		switch (ch)
   		{
   		case 'a':
   			for (i = 0; i < membercount; i++)
   			{
   				cout << member[i].fullname << endl;
   			}
   			cout << "Next Choice：";
   			break;
   		case 'b':
   			for (i = 0; i < membercount; i++)
   			{
   				cout << member[i].title << endl;
   			}
   			cout << "Next Choice：";
   			break;
   		case 'c':
   			for (i = 0; i < membercount; i++)
   			{
   				cout << member[i].bopname << endl;
   			}
   			cout << "Next Choice：";
   			break;
   		case 'd':
   			for (i = 0; i < membercount; i++)
   			{
   				switch (member[i].preference)
   				{
   				case 0: cout << member[i].fullname << endl; break;
   				case 1: cout << member[i].title << endl; break;
   				case 2: cout << member[i].bopname << endl; break;
   				}
   			}
   			cout << "Next Choice：";
   			break;
   		case 'q':
   			cout << "Bye!" << endl;
   			system("pause");
   			return 0;
   			break;
   		default:
   			cout << "Enter Your Choice：";
   			break;
   
   		}
   	}
   	system("pause");
   	return 0;
   }
   ```

5. 在Neutronia王国，货币单位是tvarp，收入所得税的计算方式如下：

   5000 tvarps：不收税

   5001～15000 tvarps：10%

   15001～35000 tvarps：15%

   35000 tvarps以上：20%

   例如，收入为38000 tvarps时，所得税为5000 0.00 + 10000 0.10 + 20000 0.15 + 3000 0.20，即4600 tvarps。请编写一个程序，使用循环来要求用户输入收入，并报告所得税。当用户输入负数或非数字时，循环将结束。

   ```c++
   #include<iostream>
   using namespace std;
   
   int main()
   {
   	double money, tax = 0;
   	cout << "请输入您的收入：" << endl;
   	while (cin >> money)
   	{
   		if (money < 0)
   		{
   			break;
   		}
   		else if (money <= 5000.0)
   		{
   			tax = 0;
   			cout << "tax = " << tax << endl;
   		}
   		else if (money <= 15000)
   		{
   			tax = (money - 5000) * 0.1;
   			cout << "tax = " << tax << endl;
   		}
   		else if (money <= 35000)
   		{
   			tax = (money - 15000) * 0.15 + 1000;
   			cout << "tax = " << tax << endl;
   		}
   		else if(money > 35000)
   		{
   			tax = (money - 35000) * 0.2 + 4000;
   			cout << "tax = " << tax << endl;
   		}
   		else
   		{
   			break;
   		}
   		cout << "请输入您的收入：" << endl;
   	}
   	
   	system("pause");
   	return 0;
   }
   ```

6. 编写一个程序，记录捐助给“维护合法权利团体”的资金。该程序要求用户输入捐献者数目，然后要求用户输入每一个捐献者的姓名和款项。这些信息被储存在一个动态分配的结构数组中。每个结构有两个成员：用来储存姓名的字符数组（或string对象）和用来存储款项的double成员。读取所有的数据后，程序将显示所有捐款超过10000的捐款者的姓名及其捐款数额。该列表前应包含一个标题，指出下面的捐款者是重要捐款人（Grand Patrons）。然后，程序将列出其他的捐款者，该列表要以Patrons开头。如果某种类别没有捐款者，则程序将打印单词“none”。该程序只显示这两种类别，而不进行排序。

   ```c++
   #include<iostream>
   #include<string>
   using namespace std;
   const int max_num = 5;
   struct donation
   {
   	string name;
   	double money;
   };
   int main()
   {
   	cout << "请输入捐献者数目：" << endl;
   	int num, gp_count = 0, p_count = 0, i;
   	cin >> num;
   	string gp_names[max_num], p_names[max_num];
   	double gp_money[max_num], p_money[max_num];
   	donation member[max_num];
   	for (int i = 0; i < num; i++)
   	{
   		cout << "请输入第 " << i + 1 << " 个捐献者的姓名和款项：" << endl;
   		cin.ignore();
   		getline(cin, member[i].name);
   		cin >> member[i].money;
   	}
   	for (i = 0; i < num; i++)
   	{
   		if (member[i].money > 10000)
   		{
   			gp_names[i] = member[i].name;
   			gp_money[i] = member[i].money;
   			gp_count++;
   		}
   		else
   		{
   			p_names[i] = member[i].name;
   			p_money[i] = member[i].money;
   			p_count++;
   		}
   	}
   	if (gp_count == 0)
   	{
   		cout << "Grand Patrons：None" << endl;
   		cout << "Patrons：" << endl;
   		for (i = 0; i < p_count; i++)
   		{
   			cout << "Patron's name：" << p_names[i] << endl;
   			cout << "Patron's donation：" << p_money[i] << endl;
   		}
   	}
   	else if (p_count == 0)
   	{
   		cout << "Grand Patrons：" << endl;
   		for (i = 0; i < gp_count; i++)
   		{
   			cout << "Grand Patron's name：" << gp_names[i] << endl;
   			cout << "Grand Patron's donation：" << gp_money[i] << endl;
   		}
   		cout << "Patrons：None" << endl;
   	}
   	else
   	{
   		cout << "Grand Patrons：" << endl;
   		for (i = 0; i < gp_count; i++)
   		{
   			cout << "Grand Patron's name：" << gp_names[i] << endl;
   			cout << "Grand Patron's donation：" << gp_money[i] << endl;
   		}
   		cout << "Patrons：" << endl;
   		for (i = 0; i < p_count; i++)
   		{
   			cout << "Patron's name：" << p_names[i] << endl;
   			cout << "Patron's donation：" << p_money[i] << endl;
   		}
   	}
   	system("pause");
   	return 0;
   }
   ```

7. 编写一个程序，它每次读取一个单词，直到用户只输入q。然后，该程序指出有多少个单词以元音打头，有多少个单词以辅音打头，还有多少个单词不属于这两类。为此，方法之一是，使用isalpha( )来区分以字母和其他字符打头的单词，然后对于通过了isalpha( )测试的单词，使用if或switch语句来确定哪些以元音打头。该程序的运行情况如下：

   ![](https://archive.biliimg.com/bfs/archive/1ed2ee27a863bedcb1eec0a17257aeabda2f9085.png)

   ```c++
   #include<iostream>
   #include<string>
   using namespace std;
   int main()
   {
   	int vowel = 0, consonant = 0, other = 0;
   	string s;
   	cout << "Enter words(q to quit)：" << endl;
   	cin >> s;
   	while (s != "q")
   	{
   		if (isalpha(s[0]))
   		{
   			if (s[0] == 'a' || s[0] == 'e' || s[0] == 'i' || s[0] == 'o' || s[0] == 'u' || s[0] == 'A' || s[0] == 'E' || s[0] == 'I' || s[0] == 'O' || s[0] == 'U')
   			{
   				vowel++;
   			}
   			else
   				consonant++;
   
   		}
   		else
   			other++;
   		cin >> s;
   	}
   	cout << vowel << " words beginning with vowels" << endl;
   	cout << consonant << " words beginning with consonants" << endl;
   	cout << other << " others" << endl;
   	system("pause");
   	return 0;
   }
   ```

8. 编写一个程序，它打开一个文件文件，逐个字符地读取该文件，直到到达文件末尾，然后指出该文件中包含多少个字符

   ```c++
   #include<iostream>
   #include<string>
   #include<fstream>
   using namespace std;
   int main()
   {
   	// 1、逐字符读取，可读取空格，但是效率较低
   	ifstream infile;
   	infile.open("test.txt", ios::in);
   	char ch;
   	int len = 0;
   	while ((ch = infile.get()) != EOF)
   	{
   		len++;
   	}
   	
   	// 2、字符串读取，逐行读取，可读取空格
   	/*ifstream infile;
   	infile.open("test.txt", ios::in);
   	string str;
   	int len = 0;
   	while (getline(infile, str))
   	{
   		len += str.length();
   	}
   	*/
   	cout << "该文件包含 " << len << " 个字符" << endl;
   	system("pause");
   	return 0;
   }
   ```

9. 完成编程练习6，但从文件中读取所需的信息。该文件的第一项应为捐款人数，余下的内容应为成对的行。在每一对中，第一行为捐款人姓名，第二行为捐款数额。即该文件类似于下面：

   PS：==本题会报错，尚未解决==

   ![](https://archive.biliimg.com/bfs/archive/39cec71a6b4ee2f9e3cc01c0f928fe4a559d11dc.png)

   ```c++
   #include<iostream>
   #include<string>
   #include<fstream>
   using namespace std;
   struct donation
   {
   	string name;
   	double money;
   };
   int main()
   {
   	cout << "请输入捐献者数目：" << endl;
   	int num, gp_count = 0, p_count = 0, i;
   	string filepath;
   	ifstream infile;
   	cin >> filepath;
   	infile.open(filepath);
   	while (!infile.is_open())
   	{
   		cout << "The file path error\n";
   		cout << "Please enter the file path: \n";
   		cin >> filepath;
   		infile.open(filepath);
   	}
   	cout << "Open successful!\n";
   	infile >> num;
   
   	donation* member = new donation[num];
   
   	for (int i = 0; i < num; i++)
   	{
   		cout << "请输入第 " << i + 1 << " 个捐献者的姓名和款项：" << endl;
   		infile.get();
   		getline(infile, member[i].name);
   		infile >> member[i].money;
   	}
   	cout << "Grand Patrons：" << endl;
   	for (i = 0; i < num; i++)
   	{
   		if (member[i].money > 10000)
   		{
   			cout << member[i].name << "\t";
   			cout << member[i].money << endl;
   			gp_count++;
   		}
   		
   	}
   
   	if (gp_count == 0)
   	{
   		cout << "None" << endl;
   		
   	}
   	cout << "Patrons：" << endl;
   	for (i = 0; i < num; i++)
   	{
   		if (member[i].money <= 10000)
   		{
   			cout << member[i].name << "\t";
   			cout << member[i].money << endl;
   			p_count++;
   		}
   
   	}
   	if (p_count == 0)
   	{
   		cout << "None" << endl;
   
   	}
   	system("pause");
   	return 0;
   }
   
   报错信息：
   0x00007FF98937CF19 处(位于 C++practice.exe 中)引发的异常: Microsoft C++ 异常: std::bad_array_new_length，位于内存位置 0x00000021868FF8B0 处。
   0x00007FF98937CF19 处(位于 C++practice.exe 中)有未经处理的异常: Microsoft C++ 异常: std::bad_array_new_length，位于内存位置 0x00000021868FF8B0 处。
   ```


## 第七章

1. 编写一个程序，不断要求用户输入两个数，直到其中的一个为0。对于每两个数，程序将使用一个函数来计算它们的调和平均数，并将结果返回给main( )，而后者将报告结果。调和平均数指的是倒数平均值的倒数，计算公式如下：调和平均数=2.0 * x * y / (x + y)

   ```c++
   #include<iostream>
   #include<string>
   using namespace std;
   double ave(double x, double y)
   {
   	return 2.0 * x * y / (x + y);
   }
   int main()
   {
   	cout << "请输入两个数：" << endl;
   	double a, b;
   	while (cin >> a >> b && (a != 0 && b != 0))
   	{
   		cout << "调和平均数为：" << ave(a, b) << endl;
   		cout << "请输入两个数：" << endl;
   	}
   	
   	system("pause");
   	return 0;
   }
   ```

   

2. 编写一个程序，要求用户输入最多10个高尔夫成绩，并将其存储在一个数组中。程序允许用户提早结束输入，并在一行上显示所有成绩，然后报告平均成绩。请使用3个数组处理函数来分别进行输入、显示和计算平均成绩。

   ```c++
   #include<iostream>
   #include<string>
   using namespace std;
   
   double* input()
   {
   	static double arr[11];
   	double* m = arr;
   	int i;
   	for (i = 0; i < 10 && cin; i++)
   	{
   		cout << "请输入第 " << i + 1 << " 个成绩：" << endl;
   		cin >> arr[i];
   		if (arr[i] < 0)
   			break;
   	}
   	if (!cin)
   	{
   		i--;
   		cin.sync();
   		cin.clear();
   	}
   	arr[i] = -1;
   	return m;
   }
   void showgrade(double* m)
   {
   	cout << "所有的分数为：" << endl;
   	for (; *m >= 0; m++)
   	{
   		cout << *m << " ";
   	}
   	cout << endl;
   }
   double average(double* m)
   {
   	double sum = 0;
   	int i = 0;
   	for (; *m >= 0; m++)
   	{
   		sum += *m;
   		i++;
   	}
   	return sum / i;
   }
   
   int main()
   {
   	double* grade = input();
   	showgrade(grade);
   	cout << "平均成绩为：" << average(grade) << endl;
   	system("pause");
   	return 0;
   }
   ```

   

1. 下面是一个结构声明：


![](https://archive.biliimg.com/bfs/archive/fcdf2d6ff05c4d599140538367ba7a43f76177e6.png)

a．编写一个函数，按值传递box结构，并显示每个成员的值。

b．编写一个函数，传递box结构的地址，并将volume成员设置为其他三维长度的乘积。

c．编写一个使用这两个函数的简单程序。

```c++
#include<iostream>
#include<string>
using namespace std;

struct box
{
	char maker[40];
	float height;
	float width;
	float length;
	float volume;
};
void show(box play)
{
	cout << "制造商：" << play.maker << endl;
	cout << "高度：" << play.height << endl;
	cout << "宽度：" << play.width << endl;
	cout << "长度：" << play.length << endl;
	cout << "体积：" << play.volume << endl;
}
float volumevalue(box* play)
{
	play->volume = play->height * play->width * play->length;
	return play->volume;
	
}
int main()
{
	box play;
	cout << "请输入制造商：";
	cin.getline(play.maker, 40);
	cout << "请输入高度：";
	cin >> play.height;
	cout << "请输入宽度：";
	cin >> play.width;
	cout << "请输入长度：";
	cin >> play.length;
	cout << "体积为：" << volumevalue(&play);
	show(play);
	system("pause");
	return 0;
}
```

   1. 许多州的彩票发行机构都使用如程序清单7.4所示的简单彩票玩法的变体。在这些玩法中，玩家从一组被称为域号码（field number）的号码中选择几个。例如，可以从域号码1～47中选择5个号码；还可以从第二个区间（如1～27）选择一个号码（称为特选号码）。要赢得头奖，必须正确猜中所有的号码。中头奖的几率是选中所有域号码的几率与选中特选号码几率的乘积。例如，在这个例子中，中头奖的几率是从47个号码中正确选取5个号码的几率与从27个号码中正确选择1个号码的几率的乘积。请修改程序清单7.4，以计算中得这种彩票头奖的几率。
      $$
      某个区间获奖的概率为：\frac{picks!}{numbers*(number-1)*(number-2)*....*(number-picks+1)}
      $$

      ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      
      double prob(double a, double b)
      {
      	double result = 1.0;
      	for (a, b; b > 0; a--, b--)
      	{
      		result = result * a / b;
      	}
      	return result;
      }
      int main()
      {
      	double p[2], total, choices;
      	cout << "Game begin：" << endl;
      	while (cin)
      	{
      		for (int i = 0; i < 2; i++)
      		{
      			cout << "请输入第 " << i + 1 << " 次的域号码和所选号码：";
      			cin >> total >> choices;
      			p[i] = prob(total, choices);
      		}
      		cout << "You have one chance in " << p[0] * p[1] << " of winning" << endl;
      		cout << "Game once again(q to quit)" << endl;
      	}
      	
      	cout << "Bye!" << endl;
      	system("pause");
      	return 0;
      }
      ```

   2. 定义一个递归函数，接受一个整数参数，并返回该参数的阶乘。前面讲过，3的阶乘写作3!，等于3*2!，依此类推；而0!被定义为1。通用的计算公式是，如果n大于零，则n!=n*（n−1）!。在程序中对该函数进行测试，程序使用循环让用户输入不同的值，程序将报告这些值的阶乘。

      ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      
      int factorial(int n)
      {
      	if (n > 1)
      	{
      		return n * factorial(n - 1);
      	}
      	else
      	{
      		return 1;
      	}
      }
      int main()
      {
      	int i;
      	cout << "请输入一个整数：";
      	while (cin >> i)
      	{
      		cout << i << " 的阶乘为：" << factorial(i) << endl;
      		cout << "请输入一个整数（q to quit）：";
      	}
      	system("pause");
      	return 0;
      }
      ```

   3. 编写一个程序，它使用下列函数：

      Fill_array( )将一个double数组的名称和长度作为参数。它提示用户输入double值，并将这些值存储到数组中。当数组被填满或用户输入了非数字时，输入将停止，并返回实际输入了多少个数字。

      Show_array( )将一个double数组的名称和长度作为参数，并显示该数组的内容。

      Reverse-array( )将一个double数组的名称和长度作为参数，并将存储在数组中的值的顺序反转。

      程序将使用这些函数来填充数组，然后显示数组；反转数组，然后显示数组；反转数组中除第一个和最后一个元素之外的所有元素，然后显示数组。

      **方法一：（==Reverse_array函数返回的是反转后的数组的地址==，要求不能输入非数字，输入数量恰好=NUM）**

      ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      const int NUM = 5;
      int Fill_array(double* arr, int len)
      {
      	double x;
      	static int i;
      	for (i = 0; cin && i < len; arr++, i++)
      	{
      		cout << "请输入一个数：";
      		cin >> x;
      		*arr = x;
      	}
      	cout << "总共输入了 " << i << " 个数字" << endl;
      	return i;
      }
      void Show_array(double* arr, int len)
      {
      	cout << "该数组的内容为：";
      	for (int i = 0; i < len; arr++, i++)
      	{
      		cout << *arr << " ";
      	}
      	cout << endl;
      }
      //void Reverse_array(double* arr, int len)
      //{
      //	double temp;
      //	for (i = 0; i < len / 2; i++)
      //	{
      //		temp = arr[i];
      //		arr[i] = arr[len - 1 - i];
      //		arr[len - 1 - i] = temp;
      //	}
      //}
      double* Reverse_array(double* arr)
      {
      	static double reversearray[4];
      	int len = NUM;
      	reversearray[0] = arr[0];
      	reversearray[len-1] = arr[len-1];
      	for (int i = 1; i < len-1; i++)
      	{
      		reversearray[i] = arr[len - i - 1];
      	}
      	return reversearray;
      }
      int main()
      {
      	double arr[NUM];
      	double* r;
      	int n;
      	n = Fill_array(arr, NUM);
      	Show_array(arr, n);
      	r = Reverse_array(arr);
      	for (int j = 0; j < n; j++,r++)
      	{
      		cout << "反转后第 " << j + 1 << " 个元素为：" << *r << endl;
      	}
      	system("pause");
      	return 0;
      }
      ```

      **方法二：（==Reverse_array函数不返回任何值，直接对arr数组进行反转==）**

      ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      const int NUM = 5;
      int Fill_array(double* arr, int len)
      {
      	double x;
      	static int i;
      	for (i = 0; cin && i < len; arr++, i++)
      	{
      		cout << "请输入一个数：";
      		cin >> x;
      		*arr = x;
      		while (cin.fail())  //版本一：只要输入的不是double型值，则一直提示用户输入，直到输入double型值
      		{
      			cin.clear();//清除cin的错误信息
      			cin.ignore();//忽略掉缓冲区的内容,置于EOF位置
      			cout << "请输入正确的数字（double型）:";
      			cin.ignore();//EOF位置，接收下一个cin函数
      			cin >> x;
      		}
      	}
      	//if (!cin)   //版本二：不提示用户输入错了，直接停止输入
      	//{
      	//	cin.clear();
      	//	i--;   //如果最后的输入不是double型的值，则输入总数i要减1
      	//}
      	cout << "总共输入了 " << i << " 个数字" << endl;
      	return i;
      }
      void Show_array(double* arr, int len)
      {
      	cout << "该数组的内容为：";
      	for (int i = 0; i < len; arr++, i++)
      	{
      		cout << *arr << " ";
      	}
      	cout << endl;
      }
      void Reverse_array(double* arr, int len)
      {
      	double temp;
      	for (int i = 0; i < len / 2; i++)
      	{
      		temp = arr[i];
      		arr[i] = arr[len - 1 - i];
      		arr[len - 1 - i] = temp;
      	}
      }
      //double* Reverse_array(double* arr)
      //{
      //	static double reversearray[4];
      //	int len = NUM;
      //	reversearray[0] = arr[0];
      //	reversearray[len-1] = arr[len-1];
      //	for (int i = 1; i < len-1; i++)
      //	{
      //		reversearray[i] = arr[len - i - 1];
      //	}
      //	return reversearray;
      //}
      int main()
      {
      	double arr[NUM];
      	int n;
      	n = Fill_array(arr, NUM);
      	Show_array(arr, n);
      	Reverse_array(arr, n);
      	double x;
      	x = arr[0];
      	arr[0] = arr[n - 1];
      	arr[n - 1] = x;
      	Show_array(arr, n);
      	system("pause");
      	return 0;
      }
      ```

   4. 修改程序清单7.7中的3个数组处理函数，使之使用两个指针参数来表示区间。fill_array( )函数不返回实际读取了多少个数字，而是返回一个指针，该指针指向最后被填充的位置；其他的函数可以将该指针作为第二个参数，以标识数据结尾

      ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      const int NUM = 5;
      double* Fill_array(double* arr, int len)
      {
      	int i;
      	for (i = 0; i < len; i++)
      	{
      		cout << "请输入一个数：";
      		cin >> arr[i];
      		if (!cin)
      		{
      			cin.clear();
      			cin.sync();
      			cout << "输入错误，输入结束..." << endl;
      			break;
      		}
      		else if (arr[i] < 0)
      		{
      			cout << "你输入了负数，输入结束..." << endl;
      			break;
      		}
      	}
      	double* a = &arr[i - 1];
      	return a;
      }
      void Show_array(double* arr, double *a)
      {
      	cout << "该数组的内容为：";
      	while(arr!=(a+1))
      	{
      		cout << *arr << " ";
      		arr++;
      	}
      	cout << endl;
      }
      void revalue(double* arr, double *a, double r)
      {
      	cout << "修改后的值为：";
      	while (arr != (a + 1))
      	{
      		cout << ((*arr) *= r) << " ";
      		arr++;
      	}
      	cout << endl;
      }
      
      int main()
      {
      	double arr[NUM];
      	double *n = Fill_array(arr, NUM);
      	Show_array(arr, n);
      	if (n == arr - 1)
      	{
      		cout << "你没有输入有效数字，所以无法变换。" << endl;
      	}
      	else
      	{
      		cout << "请输入变换因子：";
      		double r;
      		cin >> r;
      		if (!cin)
      		{
      			cout << "您输入的为字母，无法变换" << endl;
      			cin.clear();
      			cin.sync();
      		}
      		else if (r < 0)
      		{
      			cout << "您输入的为负数，无法变换" << endl;
      		}
      		else
      			revalue(arr, n, r);
      	}
      	system("pause");
      	return 0;
      }
      ```

   5. 在不使用array类的情况下完成程序清单7.15所做的工作。编写两个这样的版本：

      a．使用const char *数组存储表示季度名称的字符串，并使用double数组存储开支。

      b．使用const char *数组存储表示季度名称的字符串，并使用一个结构，该结构只有一个成员——一个用于存储开支的double数组。这种设计与使用array类的基本设计类似。

      **a题：**

      ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      const int seasons = 4;
      
      void fill(double* exp, char names[][20])
      {
      	for (int i = 0; i < seasons; i++)
      	{
      		cout << "请输入" << names[i] << "季度的开销：";
      		cin >> exp[i];
      	}
      }
      void show(double* exp, char names[][20])
      {
      	double sum = 0;
      	for (int i = 0; i < seasons; i++)
      	{
      		cout << names[i] << "季度的开销为：" << exp[i] << endl;
      		sum += exp[i];
      	}
      	cout << "总开销为：" << sum << endl;
      }
      int main()
      {
      	char snames[seasons][20] = { "Spring", "Summer", "Fall", "Winter" };
      	char(*Snames)[20] = snames;
      	double expenses[seasons];
      	fill(expenses, Snames);
      	show(expenses, Snames);
      	system("pause");
      	return 0;
      }
      ```

      **b题：**

      ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      const int seasons = 4;
      struct Expenses
      {
      	double expense[seasons];
      };
      void fill(struct Expenses *exp, char names[][20])
      {
      	for (int i = 0; i < seasons; i++)
      	{
      		cout << "请输入" << names[i] << "季度的开销：";
      		cin >> exp->expense[i];
      	}
      }
      void show(struct Expenses* exp, char names[][20])
      {
      	double sum = 0;
      	for (int i = 0; i < seasons; i++)
      	{
      		cout << names[i] << "季度的开销为：" << exp->expense[i] << endl;
      		sum += exp->expense[i];
      	}
      	cout << "总开销为：" << sum << endl;
      }
      int main()
      {
      	char snames[seasons][20] = { "Spring", "Summer", "Fall", "Winter" };
      	char(*Snames)[20] = snames;
      	Expenses expenses;
      	fill(&expenses, Snames);
      	show(&expenses, Snames);
      	system("pause");
      	return 0;
      }
      ```

   6. 这个练习让您编写处理数组和结构的函数。下面是程序的框架，请提供其中描述的函数，以完成该程序。

      <img src="https://cdn.ipfsscan.io/weibo/oslarge/008y0Zlrly1hhph0phxg2j307601i3yi.jpg" style="zoom:200%;" />

      ![](https://cdn.ipfsscan.io/weibo/oslarge/008y0Zlrly1hhph0u0kdpj30ns186aiv.jpg)

      ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      const int SLEN = 30;
      struct student
      {
      	char fullname[SLEN];
      	char hobby[SLEN];
      	int ooplevel;
      };
      int getinfo(student pa[], int n)
      {
      	int i;
      	for (i = 0; i < n; i++)
      	{
      		cout << "请输入第 " << i + 1 << " 个学生的全名：";
      		cin.getline(pa[i].fullname, SLEN);
      		if (pa[i].fullname[0] == ' ')
      		{
      			break;
      		}
      		cout << "请输入第 " << i + 1 << " 个学生的爱好：";
      		cin.getline(pa[i].hobby, SLEN);
      		cout << "请输入第 " << i + 1 << " 个学生的OOP水平：";
      		cin>>pa[i].ooplevel;
      		cin.ignore();
      		cout << endl;
      		
      	}
      	return (i-1);
      }
      void display1(student st)
      {
      	cout << "该学生的信息为：" << endl;
      	cout << "全名：" << st.fullname;
      	cout << "爱好：" << st.hobby;
      	cout << " OOPlevel：" << st.ooplevel;
      	cout << endl;
      }
      void display2(const student* ps)
      {
      	cout << "该学生的信息为：" << endl;
      	cout << "全名：" << ps->fullname;
      	cout << "爱好：" << ps->hobby;
      	cout << " OOPlevel：" << ps->ooplevel;
      	cout << endl;
      }
      void display3(const student pa[], int n)
      {
      	for (int i = 0; i < n; i++, pa++)
      	{
      		cout << "该学生的信息为：" << endl;
      		cout << "全名：" << pa->fullname;
      		cout << "爱好：" << pa->hobby;
      		cout << " OOPlevel：" << pa->ooplevel;
      		cout << endl;
      	}
      }
      int main()
      {
      	cout << "Enter class size：" << endl;
      	int class_size;
      	cin >> class_size;
      	while (cin.get() != '\n')
      		continue;
      	student* ptr_stu = new student[class_size];
      	int entered = getinfo(ptr_stu,class_size);
      	for (int i = 0; i < entered; i++)
      	{
      		display1(ptr_stu[i]);
      		display2(&ptr_stu[i]);
      	}
      	display3(ptr_stu,entered);
      	delete[]ptr_stu;
      	cout << "Done\n";
      	system("pause");
      	return 0;
      }
      ```

   7. 设计一个名为calculate( )的函数，它接受两个double值和一个指向函数的指针，而被指向的函数接受两个double参数，并返回一个double值。calculate( )函数的类型也是double，并返回被指向的函数使用calculate( )的两个double参数计算得到的值。例如，假设add( )函数的定义如下：

      ![](https://archive.biliimg.com/bfs/archive/afa7e7fedc4d0fcdb859b62e36a4e500639efdd7.png)

      则下述代码中的函数调用将导致calculate( )把2.5和10.4传递给add( )函数，并返回add( )的返回值（12.9）：

      ![](https://archive.biliimg.com/bfs/archive/deeaef24dff6bd68711141c35dd26b0b8351888a.png)

      请编写一个程序，它调用上述两个函数和至少另一个与add( )类似的函数。该程序使用循环来让用户成对地输入数字。对于每对数字，程序都使用calculate( )来调用add( )和至少一个其他的函数。如果读者爱冒险，可以尝试创建一个指针数组，其中的指针指向add( )样式的函数，并编写一个循环，使用这些指针连续让calculate( )调用这些函数。提示：下面是声明这种指针数组的方式，其中包含三个指针：

      ![](https://archive.biliimg.com/bfs/archive/48a6d720efc20fe7315d0bff0116527ee8deb0f3.png)

      可以采用数组初始化语法，并将函数名作为地址来初始化这样的数组。

      ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      double add(double x, double y)
      {
      	return x + y;
      }
      double subtraction(double x, double y)
      {
      	return x - y;
      }
      double calculate(double x, double y, double (*fun)(double, double))
      {
      	double result = fun(x, y);
      	return result;
      }
      int main()
      {
      	double x, y;
      	cout << "请输入两个数：";
      	double(*fun[2])(double, double) = { add,subtraction };
      	while (cin >> x >> y)
      	{
      		for (int i = 0; i < 2; i++)
      		{
      			if (i == 0)
      				cout << "调用add函数：" << calculate(x, y, *fun[i]) << endl;
      			else
      				cout << "调用subtraction函数：" << calculate(x, y, *fun[i]) << endl;
      		}
      		cout << "请输入两个数：";
      	}
      	system("pause");
      	return 0;
      }
      ```


## 第八章

1. 编写通常接受一个参数（字符串的地址），并打印该字符串的函数。然而，如果提供了第二个参数（int类型），且该参数不为0，则该函数打印字符串的次数将为该函数被调用的次数（注意，字符串的打印次数不等于第二个参数的值，而等于函数被调用的次数）。是的，这是一个非常可笑的函数，但它让您能够使用本章介绍的一些技术。在一个简单的程序中使用该函数，以演示该函数是如何工作的。

   ```c++
   #include<iostream>
   #include<string>
   using namespace std;
   void print(char* str, int n = 0)
   {
   	int i;
   	if (n == 0)
   	{
   		cout << str << endl;
   	}
   	else
   	{
   		for (i = 0; i < n; i++)
   		{
   			cout << str << endl;
   		}
   	}
   }
   int main()
   {
   	char str[] = "hello world";
   	int n;
   	cout << "请输入n的值：";
   	cin >> n;
   	print(str, n);
   	system("pause");
   	return 0;
   }
   ```

   

2. CandyBar结构包含3个成员。第一个成员存储candy bar的品牌名称；第二个成员存储candy bar的重量（可能有小数）；第三个成员存储candy bar的热量（整数）。请编写一个程序，它使用一个这样的函数，即将CandyBar的引用、char指针、double和int作为参数，并用最后3个值设置相应的结构成员。最后3个参数的默认值分别为“Millennium Munch”、2.85和350。另外，该程序还包含一个以CandyBar的引用为参数，并显示结构内容的函数。请尽可能使用const。

   ```c++
   #include<iostream>
   #include<string>
   using namespace std;
   struct candybar
   {
   	string brand;
   	double weight;
   	int cal;
   };
   void fill(candybar& cb, const char* brand = "Millennium Munch", const double weight = 2.85, const int cal = 350)
   {
   	cb.brand = brand;
   	cb.weight = weight;
   	cb.cal = cal;
   }
   void show(candybar& cb)
   {
   	cout << "show函数输出：" << endl;
   	cout << cb.brand << endl;
   	cout << cb.weight << endl;
   	cout << cb.cal << endl;
   }
   int main()
   {
   	candybar food;
   	const char* str = new char[20];
   	str = "icecream";
   	fill(food, str, 1.0, 300);
   	show(food);
   	system("pause");
   	return 0;
   }
   ```

3. 编写一个函数，它接受一个指向string对象的引用作为参数，并将该string对象的内容转换为大写，为此可使用表6.4描述的函数toupper( )。然后编写一个程序，它通过使用一个循环让您能够用不同的输入来测试这个函数，该程序的运行情况如下：

   ![](https://cdn.ipfsscan.io/weibo/oslarge/008y0Zlrly1hhrt5gwgh5j30d3059dgc.jpg)

   ```c++
   #include<iostream>
   #include<string>
   using namespace std;
   void upper(string& str)
   {
   	for(int i = 0; i < str.size(); i++)
   	{
   		str[i] = toupper(str[i]);
   	}
   	cout << str << endl;
   }
   int main()
   {
   	string str;
   	cout << "Enter a string(q to quit)：";
   	while (getline(cin, str) && str[0] != 'q')
   	{
   		upper(str);
   		cout << "Next string(q to quit)：";
   	}
   	cout << "Bye" << endl;
   	system("pause");
   	return 0;
   }
   ```

4. 下面是一个程序框架：

   ![](https://archive.biliimg.com/bfs/archive/f83f25ddb7554d3679f83a00b289e28b83c12305.png)

   ![](https://archive.biliimg.com/bfs/archive/df64cf6f8c464b88bf95a2c76972d10fab886d3f.png)

   请提供其中描述的函数和原型，从而完成该程序。注意，应有两个show( )函数，每个都使用默认参数。请尽可能使用cosnt参数。set( )使用new分配足够的空间来存储指定的字符串。这里使用的技术与设计和实现类时使用的相似。（可能还必须修改头文件的名称，删除using编译指令，这取决于所用的编译器。)

   ```c++
   #include<iostream>
   #include<string>
   #include<cstring>
   using namespace std;
   struct stringy
   {
   	char* str;
   	int ct;
   };
   void set(stringy& s, char* sen)
   {
   	s.ct = strlen(sen);
   	s.str = new char[s.ct+1];
   	strcpy_s(s.str, s.ct, sen);
   }
   void show(stringy stru, int n = 1)
   {
   	for (int i = 0; i < n; i++)
   	{
   		cout << "字符串：" << stru.str << endl;
   		cout << "字符串长度：" << stru.ct << endl;
   	}
   }
   void show(const char* str="Done!", int n = 1)
   {
   	for (int i = 0; i < n; i++)
   	{
   		cout << "testing为：" << str << endl;
   	}
   }
   int main()
   {
   	stringy beany;
   	char testing[] = "Reality isn't what it used to be.";
   	set(beany, testing);
   	show(beany);
   	show(beany, 2);
   	testing[0] = 'D';
   	testing[1] = 'u';
   	show(testing);
   	show(testing, 3);
   	show("Done!");
   	system("pause");
   	return 0;
   }
   ```

5. 编写模板函数max5( )，它将一个包含5个T类型元素的数组作为参数，并返回数组中最大的元素（由于长度固定，因此可以在循环中使用硬编码，而不必通过参数来传递）。在一个程序中使用该函数，将T替换为一个包含5个int值的数组和一个包含5个dowble值的数组，以测试该函数。

   ```c++
   #include<iostream>
   #include<string>
   #include<cstring>
   #include<algorithm>
   using namespace std;
   template<typename T>
   void max5(T *array)
   {
   	T max = *max_element(array, array + 5);
   	cout << "max is " << max << endl;
   }
   int main()
   {
   	int arr[5] = { 1,4,7,9,8 };
   	double arr2[5] = { 4,8,3,6,7 };
   	max5(arr);
   	max5(arr2);
   	system("pause");
   	return 0;
   }
   ```

6. 编写模板函数maxn( )，它将由一个T类型元素组成的数组和一个表示数组元素数目的整数作为参数，并返回数组中最大的元素。在程序对它进行测试，该程序使用一个包含6个int元素的数组和一个包含4个double元素的数组来调用该函数。程序还包含一个具体化，它将char指针数组和数组中的指针数量作为参数，并返回最长的字符串的地址。如果有多个这样的字符串，则返回其中第一个字符串的地址。使用由5个字符串指针组成的数组来测试该具体化。

   ```c++
   #include<iostream>
   #include<string>
   #include<cstring>
   #include<algorithm>
   using namespace std;
   template<typename t>
   t maxn(t* array, const int n)
   {
   	return (*max_element(array, array + n));
   }
   template<>
   char* maxn(char* arr[], const int n)
   {
   	char* c = arr[0];
   	for (int i = 1; i < n; i++)
   	{
   		if (strlen(arr[i]) > strlen(c))
   			c = arr[i];
   	}
   	return c;
   }
   int main()
   {
   	int arr[6] = { 1,2,3,4,5,6 };
   	double arr2[4] = { 6,7,8,9 };
   	const char* s[5] = {
   		"aaaa",
   		"bbbbb",
   		"cccccc",
   		"ddddddd",
   		"eeeeeeee",
   	};
   	const char* str = maxn(s, 5);
   	cout << "int数组中的最大值为：" << maxn(arr, 6) << endl;
   	cout << "double数组中的最大值为：" << maxn(arr2, 4) << endl;
   	cout << "最长的字符串的地址为：" << str << endl;
   	system("pause");
   	return 0;
   }
   ```

7. 修改程序清单 8.14，使其使用两个名为 SumArray()的模板函数来返回数组元素的总和，而不是显示数组的内容。程序应显示thing的总和以及所有debt的总和。

   ```c++
   #include<iostream>
   #include<string>
   #include<cstring>
   #include<algorithm>
   using namespace std;
   struct debts
   {
   	char names[50];
   	double amount;
   };
   template<typename T>
   T sumarray(T array[], int n)
   {
   	T sum = 0;
   	for (int i = 0; i < n; i++)
   		sum += array[i];
   	cout << "调用模板函数一" << endl;
   	return sum;
   }
   template<typename T>
   T sumarray(T* array[], int n)
   {
   	static T sum = 0;
   	for (int i = 0; i < n; i++)
   		sum += *array[i];
   	cout << "调用模板函数二" << endl;
   	return sum;
   }
   int main()
   {
   	int things[6] = { 1,2,3,4,5,6 };
   	debts mr_e[3] =
   	{
   		{"tom",100.0},
   		{"jerry",200.0},
   		{"miky",300.0}
   	};
   	double* pd[3];
   	for (int i = 0; i < 3; i++)
   	{
   		pd[i] = &mr_e[i].amount;
   	}
   	cout << "things的总和为：" << sumarray(things, 6) << endl;
   	cout << "debts的总和为：" << sumarray(pd, 3) << endl;
   	system("pause");
   	return 0;
   }
   ```

